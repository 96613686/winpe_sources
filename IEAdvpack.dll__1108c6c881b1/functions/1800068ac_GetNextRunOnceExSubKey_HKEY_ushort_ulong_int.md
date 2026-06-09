# GetNextRunOnceExSubKey(HKEY__ *,ushort *,ulong,int *)

- ea: `0x1800068ac`
- end: `0x180006920`
- name: `?GetNextRunOnceExSubKey@@YAXPEAUHKEY__@@PEAGKPEAH@Z`
- size: `116`
- prototype: `void __fastcall(HKEY hKey, unsigned __int16 *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800079c0`
- `0x180009c14`

## callees

- `0x1800035c8`
- `0x1800068ac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800068d7`
- `ADVAPI32!RegCloseKey` at `0x1800068d7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000690d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000690d`

## pseudocode

```c
void __fastcall GetNextRunOnceExSubKey(HKEY hKey, unsigned __int16 *a2, unsigned int a3, int *a4)
{
  __int64 v5; // r9
  unsigned __int64 v8; // rbp
  HKEY hKeya; // [rsp+78h] [rbp+20h] BYREF

  v5 = (unsigned int)++*a4;
  hKeya = 0;
  v8 = a3;
  while ( 1 )
  {
    StringCchPrintfW(a2, v8, L"%d", v5);
    if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hKeya) )
      break;
    RegCloseKey(hKeya);
    v5 = (unsigned int)++*a4;
  }
}

```

## disassembly

```asm
0x1800068ac  push    rbx
0x1800068ae  push    rbp
0x1800068af  push    rsi
0x1800068b0  push    rdi
0x1800068b1  sub     rsp, 38h
0x1800068b5  inc     dword ptr [r9]
0x1800068b8  mov     rbx, r9
0x1800068bb  mov     r9d, [r9]
0x1800068be  mov     rdi, rdx
0x1800068c1  mov     rsi, rcx
0x1800068c4  mov     [rsp+58h+hKey], 0
0x1800068cd  mov     ebp, r8d
0x1800068d0  jmp     short loc_1800068E2
0x1800068d2  mov     rcx, [rsp+58h+hKey]; hKey
0x1800068d7  call    cs:__imp_RegCloseKey
0x1800068dd  inc     dword ptr [rbx]
0x1800068df  mov     r9d, [rbx]
0x1800068e2  lea     r8, aD; "%d"
0x1800068e9  mov     rdx, rbp; unsigned __int64
0x1800068ec  mov     rcx, rdi; unsigned __int16 *
0x1800068ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800068f4  lea     rax, [rsp+58h+hKey]
0x1800068f9  mov     r9d, 20019h; samDesired
0x1800068ff  xor     r8d, r8d; ulOptions
0x180006902  mov     [rsp+58h+phkResult], rax; phkResult
0x180006907  mov     rdx, rdi; lpSubKey
0x18000690a  mov     rcx, rsi; hKey
0x18000690d  call    cs:__imp_RegOpenKeyExW
0x180006913  test    eax, eax
0x180006915  jz      short loc_1800068D2
0x180006917  add     rsp, 38h
0x18000691b  pop     rdi
0x18000691c  pop     rsi
0x18000691d  pop     rbp
0x18000691e  pop     rbx
0x18000691f  retn
```
