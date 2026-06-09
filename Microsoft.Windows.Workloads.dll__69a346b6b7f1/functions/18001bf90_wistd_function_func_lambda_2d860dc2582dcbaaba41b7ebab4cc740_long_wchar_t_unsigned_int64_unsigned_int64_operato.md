# wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18001bf90`
- end: `0x18001c03f`
- name: `??R?$__func@V_lambda_2d860dc2582dcbaaba41b7ebab4cc740_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, WCHAR **, unsigned __int64 *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010df0`
- `0x18001bf90`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18001bfe0`
- `KERNEL32!GetModuleFileNameW` at `0x18001bfe0`
- `KERNEL32!K32GetModuleFileNameExW` at `0x18001bfc2`
- `KERNEL32!K32GetModuleFileNameExW` at `0x18001bfc2`

## string_xrefs

- `0x18001c00a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        __int64 **a4)
{
  __int64 *v4; // rdi
  unsigned __int64 v5; // rbx
  WCHAR *v6; // rdx
  void *v7; // r10
  HMODULE *v8; // rax
  DWORD ModuleFileName; // eax
  const char *v10; // r9
  __int64 v11; // rcx
  bool v12; // r8
  bool v13; // cf
  DWORD ModuleFileNameW; // eax
  char v15; // dl
  __int64 v16; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = *a3;
  v6 = *a2;
  v7 = **(void ***)(a1 + 8);
  v8 = *(HMODULE **)(a1 + 16);
  if ( v7 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v7, *v8, v6, v5);
    v11 = ModuleFileName;
    v12 = ModuleFileName == 0;
    if ( !ModuleFileName )
      goto LABEL_8;
    v13 = ModuleFileName < v5 - 1;
  }
  else
  {
    ModuleFileNameW = GetModuleFileNameW(*v8, v6, v5);
    v11 = ModuleFileNameW;
    v12 = ModuleFileNameW == 0;
    if ( !ModuleFileNameW )
      goto LABEL_8;
    v13 = ModuleFileNameW < v5;
  }
  if ( v13 )
  {
    v15 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v15 = 0;
LABEL_9:
  v16 = v11 + 1;
  if ( v12 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x20B,
             (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v10);
  if ( !v15 )
    v16 = 2 * v5;
  result = 0;
  *v4 = v16;
  return result;
}

```

## disassembly

```asm
0x18001bf90  mov     [rsp+arg_0], rbx
0x18001bf95  push    rdi
0x18001bf96  sub     rsp, 20h
0x18001bf9a  mov     rax, [rcx+8]
0x18001bf9e  mov     rdi, [r9]
0x18001bfa1  mov     rbx, [r8]
0x18001bfa4  mov     rdx, [rdx]; lpFilename
0x18001bfa7  mov     r10, [rax]
0x18001bfaa  mov     rax, [rcx+10h]
0x18001bfae  mov     rcx, [rax]; hModule
0x18001bfb1  test    r10, r10
0x18001bfb4  jz      short loc_18001BFDD
0x18001bfb6  mov     r8, rdx; lpFilename
0x18001bfb9  mov     r9d, ebx; nSize
0x18001bfbc  mov     rdx, rcx; hModule
0x18001bfbf  mov     rcx, r10; hProcess
0x18001bfc2  call    cs:__imp_K32GetModuleFileNameExW
0x18001bfc8  test    eax, eax
0x18001bfca  mov     ecx, eax
0x18001bfcc  setz    r8b
0x18001bfd0  test    eax, eax
0x18001bfd2  jz      short loc_18001BFFB
0x18001bfd4  lea     rax, [rbx-1]
0x18001bfd8  cmp     rcx, rax
0x18001bfdb  jmp     short loc_18001BFF5
0x18001bfdd  mov     r8d, ebx; nSize
0x18001bfe0  call    cs:__imp_GetModuleFileNameW
0x18001bfe6  test    eax, eax
0x18001bfe8  mov     ecx, eax
0x18001bfea  setz    r8b
0x18001bfee  test    eax, eax
0x18001bff0  jz      short loc_18001BFFB
0x18001bff2  cmp     rcx, rbx
0x18001bff5  jnb     short loc_18001BFFB
0x18001bff7  mov     dl, 1
0x18001bff9  jmp     short loc_18001BFFD
0x18001bffb  xor     dl, dl
0x18001bffd  inc     rcx
0x18001c000  test    r8b, r8b
0x18001c003  jz      short loc_18001C025
0x18001c005  mov     rcx, [rsp+28h]; this
0x18001c00a  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001c011  mov     edx, 20Bh; void *
0x18001c016  mov     rbx, [rsp+28h+arg_0]
0x18001c01b  add     rsp, 20h
0x18001c01f  pop     rdi
0x18001c020  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c025  lea     rax, [rbx+rbx]
0x18001c029  test    dl, dl
0x18001c02b  mov     rbx, [rsp+28h+arg_0]
0x18001c030  cmovz   rcx, rax
0x18001c034  xor     eax, eax
0x18001c036  mov     [rdi], rcx
0x18001c039  add     rsp, 20h
0x18001c03d  pop     rdi
0x18001c03e  retn
```
