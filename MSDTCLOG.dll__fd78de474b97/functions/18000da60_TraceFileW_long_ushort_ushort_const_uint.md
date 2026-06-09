# TraceFileW(long,ushort *,ushort const *,uint)

- ea: `0x18000da60`
- end: `0x18000db2a`
- name: `?TraceFileW@@YAXJPEAGPEBGI@Z`
- size: `202`
- prototype: `void __fastcall(int, unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e574`

## callees

- `0x18000d874`
- `0x18000da60`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000da93`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000da93`
- `msvcrt!fflush` at `0x18000dafb`
- `msvcrt!fflush` at `0x18000dafb`
- `msvcrt!fclose` at `0x18000db04`
- `msvcrt!fclose` at `0x18000db04`
- `msvcrt!fwprintf` at `0x18000daf2`
- `msvcrt!fwprintf` at `0x18000daf2`

## string_xrefs

- `0x18000dae6`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`
- `0x18000daab`: `com\complus\dtc\shared\util\stringutil.cpp`

## pseudocode

```c
void __fastcall TraceFileW(int a1, unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  FILE *v7; // rbx
  int wYear; // [rsp+20h] [rbp-78h]
  int wHour; // [rsp+28h] [rbp-70h]
  int wMinute; // [rsp+30h] [rbp-68h]
  int v11; // [rsp+38h] [rbp-60h]
  int v12; // [rsp+50h] [rbp-48h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-38h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v7 = OpenTraceFile();
  if ( v7 )
  {
    v12 = a4;
    v11 = a1;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wYear = SystemTime.wYear;
    fwprintf(
      v7,
      L"%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
      SystemTime.wMonth,
      SystemTime.wDay,
      wYear,
      wHour,
      wMinute,
      v11,
      a2,
      L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
      v12);
    fflush(v7);
    fclose(v7);
  }
}

```

## disassembly

```asm
0x18000da60  mov     [rsp+arg_10], rbx
0x18000da65  push    rbp
0x18000da66  push    rsi
0x18000da67  push    rdi
0x18000da68  sub     rsp, 80h
0x18000da6f  mov     rax, cs:__security_cookie
0x18000da76  xor     rax, rsp
0x18000da79  mov     [rsp+98h+var_28], rax
0x18000da7e  mov     edi, ecx
0x18000da80  xorps   xmm0, xmm0
0x18000da83  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18000da88  mov     ebp, r9d
0x18000da8b  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18000da90  mov     rsi, rdx
0x18000da93  call    cs:__imp_GetLocalTime
0x18000da99  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x18000da9e  mov     rbx, rax
0x18000daa1  test    rax, rax
0x18000daa4  jz      short loc_18000DB0A
0x18000daa6  movzx   ecx, [rsp+98h+SystemTime.wMinute]
0x18000daab  lea     rax, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\string"...
0x18000dab2  movzx   edx, [rsp+98h+SystemTime.wHour]
0x18000dab7  movzx   r10d, [rsp+98h+SystemTime.wYear]
0x18000dabd  movzx   r9d, [rsp+98h+SystemTime.wDay]
0x18000dac3  movzx   r8d, [rsp+98h+SystemTime.wMonth]
0x18000dac9  mov     [rsp+98h+var_48], ebp
0x18000dacd  mov     [rsp+98h+var_50], rax
0x18000dad2  mov     [rsp+98h+var_58], rsi
0x18000dad7  mov     [rsp+98h+var_60], edi
0x18000dadb  mov     [rsp+98h+var_68], ecx
0x18000dadf  mov     rcx, rbx; Stream
0x18000dae2  mov     [rsp+98h+var_70], edx
0x18000dae6  lea     rdx, a02ld02ld04ld02; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x18000daed  mov     [rsp+98h+var_78], r10d
0x18000daf2  call    cs:__imp_fwprintf
0x18000daf8  mov     rcx, rbx; Stream
0x18000dafb  call    cs:__imp_fflush
0x18000db01  mov     rcx, rbx; Stream
0x18000db04  call    cs:__imp_fclose
0x18000db0a  mov     rcx, [rsp+98h+var_28]
0x18000db0f  xor     rcx, rsp; StackCookie
0x18000db12  call    __security_check_cookie
0x18000db17  mov     rbx, [rsp+98h+arg_10]
0x18000db1f  add     rsp, 80h
0x18000db26  pop     rdi
0x18000db27  pop     rsi
0x18000db28  pop     rbp
0x18000db29  retn
```
