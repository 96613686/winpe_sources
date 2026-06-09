# WinApiLite::GetTokenInformationBytes(void *,_TOKEN_INFORMATION_CLASS,uchar *,ulong,ulong *)

- ea: `0x180017230`
- end: `0x180017258`
- name: `?GetTokenInformationBytes@WinApiLite@@UEAAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAEKPEAK@Z`
- size: `40`
- prototype: `BOOL __fastcall(WinApiLite *this, void *, TOKEN_INFORMATION_CLASS, unsigned __int8 *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017251`

## pseudocode

```c
BOOL __fastcall WinApiLite::GetTokenInformationBytes(
        WinApiLite *this,
        void *a2,
        TOKEN_INFORMATION_CLASS a3,
        unsigned __int8 *a4,
        DWORD a5,
        unsigned int *a6)
{
  return GetTokenInformation(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180017230  push    rbx
0x180017232  mov     rax, [rsp+8+arg_28]
0x180017237  mov     r10, r9
0x18001723a  mov     r9d, [rsp+8+arg_20]
0x18001723f  mov     r11d, r8d
0x180017242  mov     rcx, rdx
0x180017245  mov     qword ptr [rsp+8+arg_20], rax
0x18001724a  mov     r8, r10
0x18001724d  mov     edx, r11d
0x180017250  pop     rbx
0x180017251  jmp     cs:__imp_GetTokenInformation
```
