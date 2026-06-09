# TraceFile(long,char *,char const *,uint)

- ea: `0x18000d998`
- end: `0x18000da59`
- name: `?TraceFile@@YAXJPEADPEBDI@Z`
- size: `193`
- prototype: `void __fastcall(int, char *, const char *, unsigned int)`
- caller_count: `32`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180003358`
- `0x1800042b4`
- `0x180004ff0`
- `0x180005560`
- `0x1800065c8`
- `0x180006ca0`
- `0x180006dd8`
- `0x1800073b4`
- `0x180009050`
- `0x180009934`
- `0x180009e6c`
- `0x18000a088`
- `0x18000a288`
- `0x18000a990`
- `0x18000aae4`
- `0x18000adf8`
- `0x18000afa8`
- `0x18000b658`
- `0x18000b798`
- `0x18000b974`
- `0x18000bc44`
- `0x18000c350`
- `0x18000c6b8`
- `0x18000c7fc`
- `0x18000d3ec`
- `0x180013566`
- `0x180013608`
- `0x180013b24`
- `0x180013e74`
- `0x180013f46`
- `0x180014042`
- `0x1800140ba`

## callees

- `0x18000d874`
- `0x18000d998`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d9cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d9cd`
- `msvcrt!fflush` at `0x18000da2f`
- `msvcrt!fflush` at `0x18000da2f`
- `msvcrt!fclose` at `0x18000da38`
- `msvcrt!fclose` at `0x18000da38`
- `msvcrt!fprintf` at `0x18000da26`
- `msvcrt!fprintf` at `0x18000da26`

## string_xrefs

- `0x18000da1a`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`

## pseudocode

```c
void __fastcall TraceFile(int a1, char *a2, const char *a3, int a4)
{
  FILE *v8; // rax
  FILE *v9; // rbx
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v8 = OpenTraceFile();
  v9 = v8;
  if ( v8 )
  {
    fprintf(
      v8,
      "%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
      SystemTime.wMonth,
      SystemTime.wDay,
      SystemTime.wYear,
      SystemTime.wHour,
      SystemTime.wMinute,
      a1,
      a2,
      a3,
      a4);
    fflush(v9);
    fclose(v9);
  }
}

```

## disassembly

```asm
0x18000d998  push    rbx
0x18000d99a  push    rbp
0x18000d99b  push    rsi
0x18000d99c  push    rdi
0x18000d99d  push    r14
0x18000d99f  sub     rsp, 80h
0x18000d9a6  mov     rax, cs:__security_cookie
0x18000d9ad  xor     rax, rsp
0x18000d9b0  mov     [rsp+0A8h+var_38], rax
0x18000d9b5  mov     edi, ecx
0x18000d9b7  xorps   xmm0, xmm0
0x18000d9ba  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x18000d9bf  mov     r14d, r9d
0x18000d9c2  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x18000d9c7  mov     rbp, r8
0x18000d9ca  mov     rsi, rdx
0x18000d9cd  call    cs:__imp_GetLocalTime
0x18000d9d3  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x18000d9d8  mov     rbx, rax
0x18000d9db  test    rax, rax
0x18000d9de  jz      short loc_18000DA3E
0x18000d9e0  movzx   ecx, [rsp+0A8h+SystemTime.wMinute]
0x18000d9e5  movzx   edx, [rsp+0A8h+SystemTime.wHour]
0x18000d9ea  movzx   r10d, [rsp+0A8h+SystemTime.wYear]
0x18000d9f0  movzx   r9d, [rsp+0A8h+SystemTime.wDay]
0x18000d9f6  movzx   r8d, [rsp+0A8h+SystemTime.wMonth]
0x18000d9fc  mov     [rsp+0A8h+var_58], r14d
0x18000da01  mov     [rsp+0A8h+var_60], rbp
0x18000da06  mov     [rsp+0A8h+var_68], rsi
0x18000da0b  mov     [rsp+0A8h+var_70], edi
0x18000da0f  mov     [rsp+0A8h+var_78], ecx
0x18000da13  mov     rcx, rax; Stream
0x18000da16  mov     [rsp+0A8h+var_80], edx
0x18000da1a  lea     rdx, Format; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x18000da21  mov     [rsp+0A8h+var_88], r10d
0x18000da26  call    cs:__imp_fprintf
0x18000da2c  mov     rcx, rbx; Stream
0x18000da2f  call    cs:__imp_fflush
0x18000da35  mov     rcx, rbx; Stream
0x18000da38  call    cs:__imp_fclose
0x18000da3e  mov     rcx, [rsp+0A8h+var_38]
0x18000da43  xor     rcx, rsp; StackCookie
0x18000da46  call    __security_check_cookie
0x18000da4b  add     rsp, 80h
0x18000da52  pop     r14
0x18000da54  pop     rdi
0x18000da55  pop     rsi
0x18000da56  pop     rbp
0x18000da57  pop     rbx
0x18000da58  retn
```
