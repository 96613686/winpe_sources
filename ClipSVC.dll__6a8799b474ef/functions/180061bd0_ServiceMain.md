# ServiceMain

- ea: `0x180061bd0`
- end: `0x180061c63`
- name: `ServiceMain`
- size: `147`
- prototype: `double __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000bfdc`
- `0x18003157c`
- `0x18005932c`
- `0x1800608e8`
- `0x180060d14`
- `0x180061bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c24`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180061c12`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180061c12`

## pseudocode

```c
double __fastcall ServiceMain(unsigned int a1, __int64 a2)
{
  int v4; // eax
  double result; // xmm0_8
  DWORD LastError; // eax
  __int64 v7; // rcx

  v4 = sub_1800608E8();
  if ( v4 >= 0 )
  {
    *(_QWORD *)&result = 0x200000020LL;
    *(_OWORD *)&ServiceStatus.dwServiceType = xmmword_1800B9100;
    *(_OWORD *)&ServiceStatus.dwWin32ExitCode = *(__int128 *)((char *)&xmmword_1800B9100 + 12);
    hServiceStatus = RegisterServiceCtrlHandlerW(L"ClipSVC", HandlerProc);
    if ( hServiceStatus )
    {
      sub_18005932C(2, 0, 20000);
      v4 = sub_180060D14(v7, a1, a2);
      if ( v4 >= 0 )
        return result;
    }
    else
    {
      LastError = GetLastError();
      v4 = sub_18003157C(LastError);
    }
  }
  return sub_18000BFDC((unsigned int)v4);
}

```

## disassembly

```asm
0x180061bd0  mov     [rsp+arg_0], rbx
0x180061bd5  push    rdi
0x180061bd6  sub     rsp, 20h
0x180061bda  mov     rbx, rdx
0x180061bdd  mov     edi, ecx
0x180061bdf  call    sub_1800608E8
0x180061be4  test    eax, eax
0x180061be6  js      short loc_180061C51
0x180061be8  movups  xmm0, cs:xmmword_1800B9100
0x180061bef  lea     rdx, HandlerProc; lpHandlerProc
0x180061bf6  movups  xmm1, cs:xmmword_1800B9100+0Ch
0x180061bfd  lea     rcx, ServiceName; "ClipSVC"
0x180061c04  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x180061c0b  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm1
0x180061c12  call    cs:RegisterServiceCtrlHandlerW
0x180061c18  mov     cs:hServiceStatus, rax
0x180061c1f  test    rax, rax
0x180061c22  jnz     short loc_180061C33
0x180061c24  call    cs:GetLastError
0x180061c2a  mov     ecx, eax
0x180061c2c  call    sub_18003157C
0x180061c31  jmp     short loc_180061C51
0x180061c33  xor     edx, edx
0x180061c35  mov     r8d, 4E20h
0x180061c3b  lea     ecx, [rdx+2]
0x180061c3e  call    sub_18005932C
0x180061c43  mov     r8, rbx
0x180061c46  mov     edx, edi
0x180061c48  call    sub_180060D14
0x180061c4d  test    eax, eax
0x180061c4f  jns     short loc_180061C58
0x180061c51  mov     ecx, eax
0x180061c53  call    sub_18000BFDC
0x180061c58  mov     rbx, [rsp+28h+arg_0]
0x180061c5d  add     rsp, 20h
0x180061c61  pop     rdi
0x180061c62  retn
```
