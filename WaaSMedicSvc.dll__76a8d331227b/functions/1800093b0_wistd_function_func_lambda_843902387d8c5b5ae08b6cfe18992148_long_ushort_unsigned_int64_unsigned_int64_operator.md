# wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x1800093b0`
- end: `0x18000945e`
- name: `??R?$__func@V_lambda_843902387d8c5b5ae08b6cfe18992148_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, WCHAR **, unsigned __int64 *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005964`
- `0x1800093b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009407`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009407`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800093e2`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800093e2`

## string_xrefs

- `0x18000942d`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
  __int64 v11; // r8
  bool v12; // cl
  char v13; // dl
  DWORD ModuleFileNameW; // eax
  __int64 result; // rax
  __int64 v16; // rcx
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
    if ( !ModuleFileName )
    {
      v12 = 1;
LABEL_4:
      v13 = 0;
      goto LABEL_11;
    }
    v12 = 0;
    if ( ModuleFileName >= v5 - 1 )
      goto LABEL_4;
    goto LABEL_6;
  }
  ModuleFileNameW = GetModuleFileNameW(*v8, v6, v5);
  v11 = ModuleFileNameW;
  if ( ModuleFileNameW && ModuleFileNameW < v5 )
  {
    v12 = 0;
LABEL_6:
    v13 = 1;
    goto LABEL_11;
  }
  v13 = 0;
  v12 = ModuleFileNameW == 0;
LABEL_11:
  if ( v12 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x215,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v10);
  v16 = v11 + 1;
  if ( !v13 )
    v16 = 2 * v5;
  result = 0;
  *v4 = v16;
  return result;
}

```

## disassembly

```asm
0x1800093b0  mov     [rsp+arg_0], rbx
0x1800093b5  push    rdi
0x1800093b6  sub     rsp, 20h
0x1800093ba  mov     rax, [rcx+8]
0x1800093be  mov     rdi, [r9]
0x1800093c1  mov     rbx, [r8]
0x1800093c4  mov     rdx, [rdx]; lpFilename
0x1800093c7  mov     r10, [rax]
0x1800093ca  mov     rax, [rcx+10h]
0x1800093ce  mov     rcx, [rax]; hModule
0x1800093d1  test    r10, r10
0x1800093d4  jz      short loc_180009404
0x1800093d6  mov     r8, rdx; lpFilename
0x1800093d9  mov     r9d, ebx; nSize
0x1800093dc  mov     rdx, rcx; hModule
0x1800093df  mov     rcx, r10; hProcess
0x1800093e2  call    cs:__imp_K32GetModuleFileNameExW
0x1800093e8  mov     r8d, eax
0x1800093eb  test    eax, eax
0x1800093ed  jnz     short loc_1800093F5
0x1800093ef  mov     cl, 1
0x1800093f1  xor     dl, dl
0x1800093f3  jmp     short loc_180009424
0x1800093f5  xor     cl, cl
0x1800093f7  lea     rax, [rbx-1]
0x1800093fb  cmp     r8, rax
0x1800093fe  jnb     short loc_1800093F1
0x180009400  mov     dl, 1
0x180009402  jmp     short loc_180009424
0x180009404  mov     r8d, ebx; nSize
0x180009407  call    cs:__imp_GetModuleFileNameW
0x18000940d  mov     r8d, eax
0x180009410  test    eax, eax
0x180009412  jz      short loc_18000941D
0x180009414  cmp     r8, rbx
0x180009417  jnb     short loc_18000941D
0x180009419  xor     cl, cl
0x18000941b  jmp     short loc_180009400
0x18000941d  xor     dl, dl
0x18000941f  test    eax, eax
0x180009421  setz    cl
0x180009424  test    cl, cl
0x180009426  jz      short loc_180009440
0x180009428  mov     rcx, [rsp+28h]; this
0x18000942d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009434  mov     edx, 215h; void *
0x180009439  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000943e  jmp     short loc_180009453
0x180009440  test    dl, dl
0x180009442  lea     rax, [rbx+rbx]
0x180009446  lea     rcx, [r8+1]
0x18000944a  cmovz   rcx, rax
0x18000944e  xor     eax, eax
0x180009450  mov     [rdi], rcx
0x180009453  mov     rbx, [rsp+28h+arg_0]
0x180009458  add     rsp, 20h
0x18000945c  pop     rdi
0x18000945d  retn
```
