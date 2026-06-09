# WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)

- ea: `0x180011b5c`
- end: `0x180011ced`
- name: `?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800119a0`

## callees

- `0x180008f64`
- `0x180011b5c`
- `0x180011d2c`
- `0x180011e20`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011c51`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011c51`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ccb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ccb`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180011be2`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180011be2`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180011bf6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180011bf6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180011bbc`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180011bbc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180011bd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180011bd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c8c`

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
0x180011b5c  mov     [rsp+arg_0], rbx
0x180011b61  mov     [rsp+arg_8], rbp
0x180011b66  push    rsi
0x180011b67  push    rdi
0x180011b68  push    r12
0x180011b6a  push    r14
0x180011b6c  push    r15
0x180011b6e  sub     rsp, 30h
0x180011b72  mov     r14d, ecx
0x180011b75  mov     r15, rdx
0x180011b78  xor     ecx, ecx; bstrString
0x180011b7a  call    cs:__imp_SysFreeString
0x180011b80  xor     edx, edx; int
0x180011b82  xor     ebx, ebx
0x180011b84  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180011b89  lea     r12d, [rbx+1]
0x180011b8d  mov     rsi, rax
0x180011b90  mov     ebp, r12d
0x180011b93  test    rax, rax
0x180011b96  jz      loc_180011CC9
0x180011b9c  test    rbx, rbx
0x180011b9f  jnz     loc_180011C4A
0x180011ba5  mov     ecx, r14d
0x180011ba8  lea     edx, [rbx+6]; lpType
0x180011bab  shr     ecx, 4
0x180011bae  xor     r9d, r9d; wLanguage
0x180011bb1  add     cx, r12w
0x180011bb5  movzx   r8d, cx; lpName
0x180011bb9  mov     rcx, rsi; hModule
0x180011bbc  call    cs:__imp_FindResourceExW
0x180011bc2  mov     rbx, rax
0x180011bc5  test    rax, rax
0x180011bc8  jnz     short loc_180011BCE
0x180011bca  xor     ebx, ebx
0x180011bcc  jmp     short loc_180011C2F
0x180011bce  mov     rdx, rbx; hResInfo
0x180011bd1  mov     rcx, rsi; hModule
0x180011bd4  call    cs:__imp_LoadResource
0x180011bda  test    rax, rax
0x180011bdd  jz      short loc_180011BCA
0x180011bdf  mov     rcx, rax; hResData
0x180011be2  call    cs:__imp_LockResource
0x180011be8  mov     rdi, rax
0x180011beb  test    rax, rax
0x180011bee  jz      short loc_180011BCA
0x180011bf0  mov     rdx, rbx; hResInfo
0x180011bf3  mov     rcx, rsi; hModule
0x180011bf6  call    cs:__imp_SizeofResource
0x180011bfc  mov     ecx, eax
0x180011bfe  mov     edx, r14d
0x180011c01  add     rcx, rdi; this
0x180011c04  and     edx, 0Fh
0x180011c07  jbe     short loc_180011C1E
0x180011c09  cmp     rdi, rcx
0x180011c0c  jnb     short loc_180011BCA
0x180011c0e  movzx   eax, word ptr [rdi]
0x180011c11  lea     rdi, [rdi+rax*2]
0x180011c15  add     rdi, 2
0x180011c19  add     edx, 0FFFFFFFFh
0x180011c1c  jnz     short loc_180011C09
0x180011c1e  cmp     rdi, rcx
0x180011c21  jnb     short loc_180011BCA
0x180011c23  movzx   eax, word ptr [rdi]
0x180011c26  neg     ax
0x180011c29  sbb     rbx, rbx
0x180011c2c  and     rbx, rdi
0x180011c2f  mov     edx, ebp; int
0x180011c31  add     ebp, r12d
0x180011c34  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180011c39  mov     rsi, rax
0x180011c3c  test    rax, rax
0x180011c3f  jnz     loc_180011B9C
0x180011c45  test    rbx, rbx
0x180011c48  jz      short loc_180011CC9
0x180011c4a  movzx   edx, word ptr [rbx]; ui
0x180011c4d  lea     rcx, [rbx+2]; strIn
0x180011c51  call    cs:__imp_SysAllocStringLen
0x180011c57  mov     rdi, rax
0x180011c5a  test    rax, rax
0x180011c5d  jz      short loc_180011CC9
0x180011c5f  mov     rdx, rax; unsigned __int16 *
0x180011c62  lea     rcx, [rsp+58h+pv]; this
0x180011c67  xor     ebx, ebx
0x180011c69  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180011c6e  lea     rcx, [rsp+58h+var_38]
0x180011c73  cmp     rcx, rax
0x180011c76  jz      short loc_180011C82
0x180011c78  mov     rbx, [rax]
0x180011c7b  mov     qword ptr [rax], 0
0x180011c82  mov     rcx, [rsp+58h+pv]; pv
0x180011c87  test    rcx, rcx
0x180011c8a  jz      short loc_180011C92
0x180011c8c  call    cs:__imp_CoTaskMemFree
0x180011c92  test    rbx, rbx
0x180011c95  jnz     short loc_180011CB7
0x180011c97  mov     rcx, [rsp+58h]; this
0x180011c9c  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\resource_util.h"
0x180011ca3  mov     ebx, 8007000Eh
0x180011ca8  mov     edx, 51h ; 'Q'; void *
0x180011cad  mov     r9d, ebx; char *
0x180011cb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cb5  jmp     short loc_180011CBC
0x180011cb7  mov     [r15], rbx
0x180011cba  xor     ebx, ebx
0x180011cbc  mov     rcx, rdi; bstrString
0x180011cbf  call    cs:__imp_SysFreeString
0x180011cc5  mov     eax, ebx
0x180011cc7  jmp     short loc_180011CD6
0x180011cc9  xor     ecx, ecx; bstrString
0x180011ccb  call    cs:__imp_SysFreeString
0x180011cd1  mov     eax, 80004005h
0x180011cd6  mov     rbx, [rsp+58h+arg_0]
0x180011cdb  mov     rbp, [rsp+58h+arg_8]
0x180011ce0  add     rsp, 30h
0x180011ce4  pop     r15
0x180011ce6  pop     r14
0x180011ce8  pop     r12
0x180011cea  pop     rdi
0x180011ceb  pop     rsi
0x180011cec  retn
```
