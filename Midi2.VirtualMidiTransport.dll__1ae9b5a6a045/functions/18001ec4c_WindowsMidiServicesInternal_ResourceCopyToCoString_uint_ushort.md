# WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)

- ea: `0x18001ec4c`
- end: `0x18001eddd`
- name: `?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ea90`

## callees

- `0x180009784`
- `0x18001e528`
- `0x18001ec4c`
- `0x18001ee24`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ed41`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ed41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ec6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ec6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edbb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001ece6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001ece6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ecac`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ecac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001ecc4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001ecc4`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001ecd2`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001ecd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed7c`

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
0x18001ec4c  mov     [rsp+arg_0], rbx
0x18001ec51  mov     [rsp+arg_8], rbp
0x18001ec56  push    rsi
0x18001ec57  push    rdi
0x18001ec58  push    r12
0x18001ec5a  push    r14
0x18001ec5c  push    r15
0x18001ec5e  sub     rsp, 30h
0x18001ec62  mov     r14d, ecx
0x18001ec65  mov     r15, rdx
0x18001ec68  xor     ecx, ecx; bstrString
0x18001ec6a  call    cs:__imp_SysFreeString
0x18001ec70  xor     edx, edx; int
0x18001ec72  xor     ebx, ebx
0x18001ec74  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18001ec79  lea     r12d, [rbx+1]
0x18001ec7d  mov     rsi, rax
0x18001ec80  mov     ebp, r12d
0x18001ec83  test    rax, rax
0x18001ec86  jz      loc_18001EDB9
0x18001ec8c  test    rbx, rbx
0x18001ec8f  jnz     loc_18001ED3A
0x18001ec95  mov     ecx, r14d
0x18001ec98  lea     edx, [rbx+6]; lpType
0x18001ec9b  shr     ecx, 4
0x18001ec9e  xor     r9d, r9d; wLanguage
0x18001eca1  add     cx, r12w
0x18001eca5  movzx   r8d, cx; lpName
0x18001eca9  mov     rcx, rsi; hModule
0x18001ecac  call    cs:__imp_FindResourceExW
0x18001ecb2  mov     rbx, rax
0x18001ecb5  test    rax, rax
0x18001ecb8  jnz     short loc_18001ECBE
0x18001ecba  xor     ebx, ebx
0x18001ecbc  jmp     short loc_18001ED1F
0x18001ecbe  mov     rdx, rbx; hResInfo
0x18001ecc1  mov     rcx, rsi; hModule
0x18001ecc4  call    cs:__imp_LoadResource
0x18001ecca  test    rax, rax
0x18001eccd  jz      short loc_18001ECBA
0x18001eccf  mov     rcx, rax; hResData
0x18001ecd2  call    cs:__imp_LockResource
0x18001ecd8  mov     rdi, rax
0x18001ecdb  test    rax, rax
0x18001ecde  jz      short loc_18001ECBA
0x18001ece0  mov     rdx, rbx; hResInfo
0x18001ece3  mov     rcx, rsi; hModule
0x18001ece6  call    cs:__imp_SizeofResource
0x18001ecec  mov     ecx, eax
0x18001ecee  mov     edx, r14d
0x18001ecf1  add     rcx, rdi; this
0x18001ecf4  and     edx, 0Fh
0x18001ecf7  jbe     short loc_18001ED0E
0x18001ecf9  cmp     rdi, rcx
0x18001ecfc  jnb     short loc_18001ECBA
0x18001ecfe  movzx   eax, word ptr [rdi]
0x18001ed01  lea     rdi, [rdi+rax*2]
0x18001ed05  add     rdi, 2
0x18001ed09  add     edx, 0FFFFFFFFh
0x18001ed0c  jnz     short loc_18001ECF9
0x18001ed0e  cmp     rdi, rcx
0x18001ed11  jnb     short loc_18001ECBA
0x18001ed13  movzx   eax, word ptr [rdi]
0x18001ed16  neg     ax
0x18001ed19  sbb     rbx, rbx
0x18001ed1c  and     rbx, rdi
0x18001ed1f  mov     edx, ebp; int
0x18001ed21  add     ebp, r12d
0x18001ed24  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18001ed29  mov     rsi, rax
0x18001ed2c  test    rax, rax
0x18001ed2f  jnz     loc_18001EC8C
0x18001ed35  test    rbx, rbx
0x18001ed38  jz      short loc_18001EDB9
0x18001ed3a  movzx   edx, word ptr [rbx]; ui
0x18001ed3d  lea     rcx, [rbx+2]; strIn
0x18001ed41  call    cs:__imp_SysAllocStringLen
0x18001ed47  mov     rdi, rax
0x18001ed4a  test    rax, rax
0x18001ed4d  jz      short loc_18001EDB9
0x18001ed4f  mov     rdx, rax; unsigned __int16 *
0x18001ed52  lea     rcx, [rsp+58h+pv]; this
0x18001ed57  xor     ebx, ebx
0x18001ed59  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001ed5e  lea     rcx, [rsp+58h+var_38]
0x18001ed63  cmp     rcx, rax
0x18001ed66  jz      short loc_18001ED72
0x18001ed68  mov     rbx, [rax]
0x18001ed6b  mov     qword ptr [rax], 0
0x18001ed72  mov     rcx, [rsp+58h+pv]; pv
0x18001ed77  test    rcx, rcx
0x18001ed7a  jz      short loc_18001ED82
0x18001ed7c  call    cs:__imp_CoTaskMemFree
0x18001ed82  test    rbx, rbx
0x18001ed85  jnz     short loc_18001EDA7
0x18001ed87  mov     rcx, [rsp+58h]; this
0x18001ed8c  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\resource_util.h"
0x18001ed93  mov     ebx, 8007000Eh
0x18001ed98  mov     edx, 51h ; 'Q'; void *
0x18001ed9d  mov     r9d, ebx; char *
0x18001eda0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eda5  jmp     short loc_18001EDAC
0x18001eda7  mov     [r15], rbx
0x18001edaa  xor     ebx, ebx
0x18001edac  mov     rcx, rdi; bstrString
0x18001edaf  call    cs:__imp_SysFreeString
0x18001edb5  mov     eax, ebx
0x18001edb7  jmp     short loc_18001EDC6
0x18001edb9  xor     ecx, ecx; bstrString
0x18001edbb  call    cs:__imp_SysFreeString
0x18001edc1  mov     eax, 80004005h
0x18001edc6  mov     rbx, [rsp+58h+arg_0]
0x18001edcb  mov     rbp, [rsp+58h+arg_8]
0x18001edd0  add     rsp, 30h
0x18001edd4  pop     r15
0x18001edd6  pop     r14
0x18001edd8  pop     r12
0x18001edda  pop     rdi
0x18001eddb  pop     rsi
0x18001eddc  retn
```
