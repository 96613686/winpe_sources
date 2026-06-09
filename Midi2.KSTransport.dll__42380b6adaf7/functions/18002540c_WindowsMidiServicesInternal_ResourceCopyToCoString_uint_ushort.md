# WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)

- ea: `0x18002540c`
- end: `0x18002559d`
- name: `?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025250`

## callees

- `0x18000a814`
- `0x180024cf4`
- `0x18002540c`
- `0x1800255e4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025501`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025501`
- `OLEAUT32!__imp_SysFreeString` at `0x18002542a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002556f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002557b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002542a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002556f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002557b`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800254a6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800254a6`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180025492`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180025492`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002546c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002546c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180025484`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180025484`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553c`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::ResourceCopyToCoString(
        WindowsMidiServicesInternal *this,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  unsigned int v3; // r14d
  unsigned __int16 *v5; // rbx
  ATL::CAtlBaseModule *v6; // rcx
  HMODULE HInstanceAt; // rsi
  int v8; // ebp
  HRSRC Resource; // rax
  ATL::CAtlBaseModule *v10; // rcx
  HRSRC v11; // rbx
  HGLOBAL v12; // rax
  ATL::CAtlBaseModule *v13; // rdi
  int v14; // edx
  int v15; // edx
  const unsigned __int16 *v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  OLECHAR *v19; // rdi
  __int64 v20; // rbx
  int *cotaskmem_string_nothrow; // rax
  unsigned int v22; // ebx
  int v24; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  v3 = (unsigned int)this;
  SysFreeString(0);
  v5 = 0;
  HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v6, 0);
  v8 = 1;
  if ( !HInstanceAt )
    goto LABEL_23;
  while ( !v5 )
  {
    Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((v3 >> 4) + 1), 0);
    v11 = Resource;
    if ( Resource )
    {
      v12 = LoadResource(HInstanceAt, Resource);
      if ( v12 )
      {
        v13 = (ATL::CAtlBaseModule *)LockResource(v12);
        if ( v13 )
        {
          v10 = (ATL::CAtlBaseModule *)((char *)v13 + SizeofResource(HInstanceAt, v11));
          v14 = v3 & 0xF;
          if ( (v3 & 0xF) != 0 )
          {
            while ( v13 < v10 )
            {
              v13 = (ATL::CAtlBaseModule *)((char *)v13 + 2 * *(unsigned __int16 *)v13 + 2);
              if ( !--v14 )
                goto LABEL_10;
            }
          }
          else
          {
LABEL_10:
            if ( v13 < v10 )
            {
              v5 = (unsigned __int16 *)((unsigned __int64)v13 & -(__int64)(*(_WORD *)v13 != 0));
              goto LABEL_12;
            }
          }
        }
      }
    }
    v5 = 0;
LABEL_12:
    v15 = v8++;
    HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v10, v15);
    if ( !HInstanceAt )
    {
      if ( !v5 )
        goto LABEL_23;
      break;
    }
  }
  v16 = SysAllocStringLen(v5 + 1, *v5);
  v19 = (OLECHAR *)v16;
  if ( !v16 )
  {
LABEL_23:
    SysFreeString(0);
    return 2147500037LL;
  }
  v20 = 0;
  cotaskmem_string_nothrow = (int *)wil::make_cotaskmem_string_nothrow((wil *)&pv, v16, v17, v18);
  if ( &v24 != cotaskmem_string_nothrow )
  {
    v20 = *(_QWORD *)cotaskmem_string_nothrow;
    *(_QWORD *)cotaskmem_string_nothrow = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v20 )
  {
    *a2 = v20;
    v22 = 0;
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"avcore\\midi2\\inc\\resource_util.h",
      (const char *)0x8007000ELL,
      v24);
  }
  SysFreeString(v19);
  return v22;
}

```

## disassembly

```asm
0x18002540c  mov     [rsp+arg_0], rbx
0x180025411  mov     [rsp+arg_8], rbp
0x180025416  push    rsi
0x180025417  push    rdi
0x180025418  push    r12
0x18002541a  push    r14
0x18002541c  push    r15
0x18002541e  sub     rsp, 30h
0x180025422  mov     r14d, ecx
0x180025425  mov     r15, rdx
0x180025428  xor     ecx, ecx; bstrString
0x18002542a  call    cs:__imp_SysFreeString
0x180025430  xor     edx, edx; int
0x180025432  xor     ebx, ebx
0x180025434  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180025439  lea     r12d, [rbx+1]
0x18002543d  mov     rsi, rax
0x180025440  mov     ebp, r12d
0x180025443  test    rax, rax
0x180025446  jz      loc_180025579
0x18002544c  test    rbx, rbx
0x18002544f  jnz     loc_1800254FA
0x180025455  mov     ecx, r14d
0x180025458  lea     edx, [rbx+6]; lpType
0x18002545b  shr     ecx, 4
0x18002545e  xor     r9d, r9d; wLanguage
0x180025461  add     cx, r12w
0x180025465  movzx   r8d, cx; lpName
0x180025469  mov     rcx, rsi; hModule
0x18002546c  call    cs:__imp_FindResourceExW
0x180025472  mov     rbx, rax
0x180025475  test    rax, rax
0x180025478  jnz     short loc_18002547E
0x18002547a  xor     ebx, ebx
0x18002547c  jmp     short loc_1800254DF
0x18002547e  mov     rdx, rbx; hResInfo
0x180025481  mov     rcx, rsi; hModule
0x180025484  call    cs:__imp_LoadResource
0x18002548a  test    rax, rax
0x18002548d  jz      short loc_18002547A
0x18002548f  mov     rcx, rax; hResData
0x180025492  call    cs:__imp_LockResource
0x180025498  mov     rdi, rax
0x18002549b  test    rax, rax
0x18002549e  jz      short loc_18002547A
0x1800254a0  mov     rdx, rbx; hResInfo
0x1800254a3  mov     rcx, rsi; hModule
0x1800254a6  call    cs:__imp_SizeofResource
0x1800254ac  mov     ecx, eax
0x1800254ae  mov     edx, r14d
0x1800254b1  add     rcx, rdi; this
0x1800254b4  and     edx, 0Fh
0x1800254b7  jbe     short loc_1800254CE
0x1800254b9  cmp     rdi, rcx
0x1800254bc  jnb     short loc_18002547A
0x1800254be  movzx   eax, word ptr [rdi]
0x1800254c1  lea     rdi, [rdi+rax*2]
0x1800254c5  add     rdi, 2
0x1800254c9  add     edx, 0FFFFFFFFh
0x1800254cc  jnz     short loc_1800254B9
0x1800254ce  cmp     rdi, rcx
0x1800254d1  jnb     short loc_18002547A
0x1800254d3  movzx   eax, word ptr [rdi]
0x1800254d6  neg     ax
0x1800254d9  sbb     rbx, rbx
0x1800254dc  and     rbx, rdi
0x1800254df  mov     edx, ebp; int
0x1800254e1  add     ebp, r12d
0x1800254e4  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x1800254e9  mov     rsi, rax
0x1800254ec  test    rax, rax
0x1800254ef  jnz     loc_18002544C
0x1800254f5  test    rbx, rbx
0x1800254f8  jz      short loc_180025579
0x1800254fa  movzx   edx, word ptr [rbx]; ui
0x1800254fd  lea     rcx, [rbx+2]; strIn
0x180025501  call    cs:__imp_SysAllocStringLen
0x180025507  mov     rdi, rax
0x18002550a  test    rax, rax
0x18002550d  jz      short loc_180025579
0x18002550f  mov     rdx, rax; unsigned __int16 *
0x180025512  lea     rcx, [rsp+58h+pv]; this
0x180025517  xor     ebx, ebx
0x180025519  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18002551e  lea     rcx, [rsp+58h+var_38]
0x180025523  cmp     rcx, rax
0x180025526  jz      short loc_180025532
0x180025528  mov     rbx, [rax]
0x18002552b  mov     qword ptr [rax], 0
0x180025532  mov     rcx, [rsp+58h+pv]; pv
0x180025537  test    rcx, rcx
0x18002553a  jz      short loc_180025542
0x18002553c  call    cs:__imp_CoTaskMemFree
0x180025542  test    rbx, rbx
0x180025545  jnz     short loc_180025567
0x180025547  mov     rcx, [rsp+58h]; this
0x18002554c  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\resource_util.h"
0x180025553  mov     ebx, 8007000Eh
0x180025558  mov     edx, 51h ; 'Q'; void *
0x18002555d  mov     r9d, ebx; char *
0x180025560  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025565  jmp     short loc_18002556C
0x180025567  mov     [r15], rbx
0x18002556a  xor     ebx, ebx
0x18002556c  mov     rcx, rdi; bstrString
0x18002556f  call    cs:__imp_SysFreeString
0x180025575  mov     eax, ebx
0x180025577  jmp     short loc_180025586
0x180025579  xor     ecx, ecx; bstrString
0x18002557b  call    cs:__imp_SysFreeString
0x180025581  mov     eax, 80004005h
0x180025586  mov     rbx, [rsp+58h+arg_0]
0x18002558b  mov     rbp, [rsp+58h+arg_8]
0x180025590  add     rsp, 30h
0x180025594  pop     r15
0x180025596  pop     r14
0x180025598  pop     r12
0x18002559a  pop     rdi
0x18002559b  pop     rsi
0x18002559c  retn
```
