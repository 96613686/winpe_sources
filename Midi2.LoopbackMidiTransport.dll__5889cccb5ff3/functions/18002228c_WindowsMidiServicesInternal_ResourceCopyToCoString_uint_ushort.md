# WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)

- ea: `0x18002228c`
- end: `0x18002241d`
- name: `?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800220d0`

## callees

- `0x18000a024`
- `0x18001b9ec`
- `0x18002228c`
- `0x180022464`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180022381`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180022381`
- `OLEAUT32!__imp_SysFreeString` at `0x1800222aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800223ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800223fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800222aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800223ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800223fb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180022326`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180022326`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800222ec`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800222ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180022304`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180022304`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180022312`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180022312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223bc`

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
0x18002228c  mov     [rsp+arg_0], rbx
0x180022291  mov     [rsp+arg_8], rbp
0x180022296  push    rsi
0x180022297  push    rdi
0x180022298  push    r12
0x18002229a  push    r14
0x18002229c  push    r15
0x18002229e  sub     rsp, 30h
0x1800222a2  mov     r14d, ecx
0x1800222a5  mov     r15, rdx
0x1800222a8  xor     ecx, ecx; bstrString
0x1800222aa  call    cs:__imp_SysFreeString
0x1800222b0  xor     edx, edx; int
0x1800222b2  xor     ebx, ebx
0x1800222b4  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x1800222b9  lea     r12d, [rbx+1]
0x1800222bd  mov     rsi, rax
0x1800222c0  mov     ebp, r12d
0x1800222c3  test    rax, rax
0x1800222c6  jz      loc_1800223F9
0x1800222cc  test    rbx, rbx
0x1800222cf  jnz     loc_18002237A
0x1800222d5  mov     ecx, r14d
0x1800222d8  lea     edx, [rbx+6]; lpType
0x1800222db  shr     ecx, 4
0x1800222de  xor     r9d, r9d; wLanguage
0x1800222e1  add     cx, r12w
0x1800222e5  movzx   r8d, cx; lpName
0x1800222e9  mov     rcx, rsi; hModule
0x1800222ec  call    cs:__imp_FindResourceExW
0x1800222f2  mov     rbx, rax
0x1800222f5  test    rax, rax
0x1800222f8  jnz     short loc_1800222FE
0x1800222fa  xor     ebx, ebx
0x1800222fc  jmp     short loc_18002235F
0x1800222fe  mov     rdx, rbx; hResInfo
0x180022301  mov     rcx, rsi; hModule
0x180022304  call    cs:__imp_LoadResource
0x18002230a  test    rax, rax
0x18002230d  jz      short loc_1800222FA
0x18002230f  mov     rcx, rax; hResData
0x180022312  call    cs:__imp_LockResource
0x180022318  mov     rdi, rax
0x18002231b  test    rax, rax
0x18002231e  jz      short loc_1800222FA
0x180022320  mov     rdx, rbx; hResInfo
0x180022323  mov     rcx, rsi; hModule
0x180022326  call    cs:__imp_SizeofResource
0x18002232c  mov     ecx, eax
0x18002232e  mov     edx, r14d
0x180022331  add     rcx, rdi; this
0x180022334  and     edx, 0Fh
0x180022337  jbe     short loc_18002234E
0x180022339  cmp     rdi, rcx
0x18002233c  jnb     short loc_1800222FA
0x18002233e  movzx   eax, word ptr [rdi]
0x180022341  lea     rdi, [rdi+rax*2]
0x180022345  add     rdi, 2
0x180022349  add     edx, 0FFFFFFFFh
0x18002234c  jnz     short loc_180022339
0x18002234e  cmp     rdi, rcx
0x180022351  jnb     short loc_1800222FA
0x180022353  movzx   eax, word ptr [rdi]
0x180022356  neg     ax
0x180022359  sbb     rbx, rbx
0x18002235c  and     rbx, rdi
0x18002235f  mov     edx, ebp; int
0x180022361  add     ebp, r12d
0x180022364  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180022369  mov     rsi, rax
0x18002236c  test    rax, rax
0x18002236f  jnz     loc_1800222CC
0x180022375  test    rbx, rbx
0x180022378  jz      short loc_1800223F9
0x18002237a  movzx   edx, word ptr [rbx]; ui
0x18002237d  lea     rcx, [rbx+2]; strIn
0x180022381  call    cs:__imp_SysAllocStringLen
0x180022387  mov     rdi, rax
0x18002238a  test    rax, rax
0x18002238d  jz      short loc_1800223F9
0x18002238f  mov     rdx, rax; unsigned __int16 *
0x180022392  lea     rcx, [rsp+58h+pv]; this
0x180022397  xor     ebx, ebx
0x180022399  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18002239e  lea     rcx, [rsp+58h+var_38]
0x1800223a3  cmp     rcx, rax
0x1800223a6  jz      short loc_1800223B2
0x1800223a8  mov     rbx, [rax]
0x1800223ab  mov     qword ptr [rax], 0
0x1800223b2  mov     rcx, [rsp+58h+pv]; pv
0x1800223b7  test    rcx, rcx
0x1800223ba  jz      short loc_1800223C2
0x1800223bc  call    cs:__imp_CoTaskMemFree
0x1800223c2  test    rbx, rbx
0x1800223c5  jnz     short loc_1800223E7
0x1800223c7  mov     rcx, [rsp+58h]; this
0x1800223cc  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\resource_util.h"
0x1800223d3  mov     ebx, 8007000Eh
0x1800223d8  mov     edx, 51h ; 'Q'; void *
0x1800223dd  mov     r9d, ebx; char *
0x1800223e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800223e5  jmp     short loc_1800223EC
0x1800223e7  mov     [r15], rbx
0x1800223ea  xor     ebx, ebx
0x1800223ec  mov     rcx, rdi; bstrString
0x1800223ef  call    cs:__imp_SysFreeString
0x1800223f5  mov     eax, ebx
0x1800223f7  jmp     short loc_180022406
0x1800223f9  xor     ecx, ecx; bstrString
0x1800223fb  call    cs:__imp_SysFreeString
0x180022401  mov     eax, 80004005h
0x180022406  mov     rbx, [rsp+58h+arg_0]
0x18002240b  mov     rbp, [rsp+58h+arg_8]
0x180022410  add     rsp, 30h
0x180022414  pop     r15
0x180022416  pop     r14
0x180022418  pop     r12
0x18002241a  pop     rdi
0x18002241b  pop     rsi
0x18002241c  retn
```
