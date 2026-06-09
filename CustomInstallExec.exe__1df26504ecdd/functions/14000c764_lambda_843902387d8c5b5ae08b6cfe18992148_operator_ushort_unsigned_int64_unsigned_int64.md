# _lambda_843902387d8c5b5ae08b6cfe18992148_::operator()(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x14000c764`
- end: `0x14000c80b`
- name: `??R_lambda_843902387d8c5b5ae08b6cfe18992148_@@QEBAJPEAG_KPEA_K@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64, WCHAR *, unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c820`

## callees

- `0x140006c04`
- `0x14000c764`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000c7b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000c7b4`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000c792`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000c792`

## string_xrefs

- `0x14000c7da`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall _lambda_843902387d8c5b5ae08b6cfe18992148_::operator()(
        __int64 a1,
        WCHAR *a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  void *v6; // r10
  HMODULE *v7; // rax
  DWORD ModuleFileName; // eax
  const char *v9; // r9
  __int64 v10; // r8
  bool v11; // cl
  char v12; // dl
  DWORD ModuleFileNameW; // eax
  __int64 result; // rax
  __int64 v15; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v6 = **(void ***)a1;
  v7 = *(HMODULE **)(a1 + 8);
  if ( v6 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v6, *v7, a2, a3);
    v10 = ModuleFileName;
    if ( !ModuleFileName )
    {
      v11 = 1;
LABEL_4:
      v12 = 0;
      goto LABEL_11;
    }
    v11 = 0;
    if ( ModuleFileName >= a3 - 1 )
      goto LABEL_4;
    goto LABEL_6;
  }
  ModuleFileNameW = GetModuleFileNameW(*v7, a2, a3);
  v10 = ModuleFileNameW;
  if ( ModuleFileNameW && ModuleFileNameW < a3 )
  {
    v11 = 0;
LABEL_6:
    v12 = 1;
    goto LABEL_11;
  }
  v12 = 0;
  v11 = ModuleFileNameW == 0;
LABEL_11:
  if ( v11 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x215,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v9);
  v15 = v10 + 1;
  if ( !v12 )
    v15 = 2 * a3;
  result = 0;
  *a4 = v15;
  return result;
}

```

## disassembly

```asm
0x14000c764  mov     [rsp+arg_0], rbx
0x14000c769  push    rdi
0x14000c76a  sub     rsp, 20h
0x14000c76e  mov     rax, [rcx]
0x14000c771  mov     rdi, r9
0x14000c774  mov     rbx, r8
0x14000c777  mov     r10, [rax]
0x14000c77a  mov     rax, [rcx+8]
0x14000c77e  mov     rcx, [rax]; hModule
0x14000c781  test    r10, r10
0x14000c784  jz      short loc_14000C7B4
0x14000c786  mov     r8, rdx; lpFilename
0x14000c789  mov     r9d, ebx; nSize
0x14000c78c  mov     rdx, rcx; hModule
0x14000c78f  mov     rcx, r10; hProcess
0x14000c792  call    cs:__imp_K32GetModuleFileNameExW
0x14000c798  mov     r8d, eax; nSize
0x14000c79b  test    eax, eax
0x14000c79d  jnz     short loc_14000C7A5
0x14000c79f  mov     cl, 1
0x14000c7a1  xor     dl, dl
0x14000c7a3  jmp     short loc_14000C7D1
0x14000c7a5  xor     cl, cl
0x14000c7a7  lea     rax, [rbx-1]
0x14000c7ab  cmp     r8, rax
0x14000c7ae  jnb     short loc_14000C7A1
0x14000c7b0  mov     dl, 1; lpFilename
0x14000c7b2  jmp     short loc_14000C7D1
0x14000c7b4  call    cs:__imp_GetModuleFileNameW
0x14000c7ba  mov     r8d, eax
0x14000c7bd  test    eax, eax
0x14000c7bf  jz      short loc_14000C7CA
0x14000c7c1  cmp     r8, rbx
0x14000c7c4  jnb     short loc_14000C7CA
0x14000c7c6  xor     cl, cl
0x14000c7c8  jmp     short loc_14000C7B0
0x14000c7ca  xor     dl, dl
0x14000c7cc  test    eax, eax
0x14000c7ce  setz    cl
0x14000c7d1  test    cl, cl
0x14000c7d3  jz      short loc_14000C7ED
0x14000c7d5  mov     rcx, [rsp+28h]; this
0x14000c7da  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000c7e1  mov     edx, 215h; void *
0x14000c7e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c7eb  jmp     short loc_14000C800
0x14000c7ed  test    dl, dl
0x14000c7ef  lea     rax, [rbx+rbx]
0x14000c7f3  lea     rcx, [r8+1]
0x14000c7f7  cmovz   rcx, rax
0x14000c7fb  xor     eax, eax
0x14000c7fd  mov     [rdi], rcx
0x14000c800  mov     rbx, [rsp+28h+arg_0]
0x14000c805  add     rsp, 20h
0x14000c809  pop     rdi
0x14000c80a  retn
```
