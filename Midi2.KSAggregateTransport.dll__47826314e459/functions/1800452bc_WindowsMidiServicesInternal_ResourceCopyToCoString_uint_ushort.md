# WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)

- ea: `0x1800452bc`
- end: `0x18004544d`
- name: `?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045100`

## callees

- `0x18000b394`
- `0x18001f6f8`
- `0x1800452bc`
- `0x1800460b8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800453b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800453b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800452da`
- `OLEAUT32!__imp_SysFreeString` at `0x18004541f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004542b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800452da`
- `OLEAUT32!__imp_SysFreeString` at `0x18004541f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004542b`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180045356`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180045356`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18004531c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18004531c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180045342`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180045342`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180045334`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180045334`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800453ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800453ec`

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
0x1800452bc  mov     [rsp+arg_0], rbx
0x1800452c1  mov     [rsp+arg_8], rbp
0x1800452c6  push    rsi
0x1800452c7  push    rdi
0x1800452c8  push    r12
0x1800452ca  push    r14
0x1800452cc  push    r15
0x1800452ce  sub     rsp, 30h
0x1800452d2  mov     r14d, ecx
0x1800452d5  mov     r15, rdx
0x1800452d8  xor     ecx, ecx; bstrString
0x1800452da  call    cs:__imp_SysFreeString
0x1800452e0  xor     edx, edx; int
0x1800452e2  xor     ebx, ebx
0x1800452e4  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x1800452e9  lea     r12d, [rbx+1]
0x1800452ed  mov     rsi, rax
0x1800452f0  mov     ebp, r12d
0x1800452f3  test    rax, rax
0x1800452f6  jz      loc_180045429
0x1800452fc  test    rbx, rbx
0x1800452ff  jnz     loc_1800453AA
0x180045305  mov     ecx, r14d
0x180045308  lea     edx, [rbx+6]; lpType
0x18004530b  shr     ecx, 4
0x18004530e  xor     r9d, r9d; wLanguage
0x180045311  add     cx, r12w
0x180045315  movzx   r8d, cx; lpName
0x180045319  mov     rcx, rsi; hModule
0x18004531c  call    cs:__imp_FindResourceExW
0x180045322  mov     rbx, rax
0x180045325  test    rax, rax
0x180045328  jnz     short loc_18004532E
0x18004532a  xor     ebx, ebx
0x18004532c  jmp     short loc_18004538F
0x18004532e  mov     rdx, rbx; hResInfo
0x180045331  mov     rcx, rsi; hModule
0x180045334  call    cs:__imp_LoadResource
0x18004533a  test    rax, rax
0x18004533d  jz      short loc_18004532A
0x18004533f  mov     rcx, rax; hResData
0x180045342  call    cs:__imp_LockResource
0x180045348  mov     rdi, rax
0x18004534b  test    rax, rax
0x18004534e  jz      short loc_18004532A
0x180045350  mov     rdx, rbx; hResInfo
0x180045353  mov     rcx, rsi; hModule
0x180045356  call    cs:__imp_SizeofResource
0x18004535c  mov     ecx, eax
0x18004535e  mov     edx, r14d
0x180045361  add     rcx, rdi; this
0x180045364  and     edx, 0Fh
0x180045367  jbe     short loc_18004537E
0x180045369  cmp     rdi, rcx
0x18004536c  jnb     short loc_18004532A
0x18004536e  movzx   eax, word ptr [rdi]
0x180045371  lea     rdi, [rdi+rax*2]
0x180045375  add     rdi, 2
0x180045379  add     edx, 0FFFFFFFFh
0x18004537c  jnz     short loc_180045369
0x18004537e  cmp     rdi, rcx
0x180045381  jnb     short loc_18004532A
0x180045383  movzx   eax, word ptr [rdi]
0x180045386  neg     ax
0x180045389  sbb     rbx, rbx
0x18004538c  and     rbx, rdi
0x18004538f  mov     edx, ebp; int
0x180045391  add     ebp, r12d
0x180045394  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180045399  mov     rsi, rax
0x18004539c  test    rax, rax
0x18004539f  jnz     loc_1800452FC
0x1800453a5  test    rbx, rbx
0x1800453a8  jz      short loc_180045429
0x1800453aa  movzx   edx, word ptr [rbx]; ui
0x1800453ad  lea     rcx, [rbx+2]; strIn
0x1800453b1  call    cs:__imp_SysAllocStringLen
0x1800453b7  mov     rdi, rax
0x1800453ba  test    rax, rax
0x1800453bd  jz      short loc_180045429
0x1800453bf  mov     rdx, rax; unsigned __int16 *
0x1800453c2  lea     rcx, [rsp+58h+pv]; this
0x1800453c7  xor     ebx, ebx
0x1800453c9  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800453ce  lea     rcx, [rsp+58h+var_38]
0x1800453d3  cmp     rcx, rax
0x1800453d6  jz      short loc_1800453E2
0x1800453d8  mov     rbx, [rax]
0x1800453db  mov     qword ptr [rax], 0
0x1800453e2  mov     rcx, [rsp+58h+pv]; pv
0x1800453e7  test    rcx, rcx
0x1800453ea  jz      short loc_1800453F2
0x1800453ec  call    cs:__imp_CoTaskMemFree
0x1800453f2  test    rbx, rbx
0x1800453f5  jnz     short loc_180045417
0x1800453f7  mov     rcx, [rsp+58h]; this
0x1800453fc  lea     r8, aAvcoreMidi2Inc_0; "avcore\\midi2\\inc\\resource_util.h"
0x180045403  mov     ebx, 8007000Eh
0x180045408  mov     edx, 51h ; 'Q'; void *
0x18004540d  mov     r9d, ebx; char *
0x180045410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045415  jmp     short loc_18004541C
0x180045417  mov     [r15], rbx
0x18004541a  xor     ebx, ebx
0x18004541c  mov     rcx, rdi; bstrString
0x18004541f  call    cs:__imp_SysFreeString
0x180045425  mov     eax, ebx
0x180045427  jmp     short loc_180045436
0x180045429  xor     ecx, ecx; bstrString
0x18004542b  call    cs:__imp_SysFreeString
0x180045431  mov     eax, 80004005h
0x180045436  mov     rbx, [rsp+58h+arg_0]
0x18004543b  mov     rbp, [rsp+58h+arg_8]
0x180045440  add     rsp, 30h
0x180045444  pop     r15
0x180045446  pop     r14
0x180045448  pop     r12
0x18004544a  pop     rdi
0x18004544b  pop     rsi
0x18004544c  retn
```
