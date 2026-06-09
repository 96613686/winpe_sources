# CSession::_CreateReaderActionWait(void)

- ea: `0x18000da20`
- end: `0x18000db18`
- name: `?_CreateReaderActionWait@CSession@@AEAAJXZ`
- size: `248`
- prototype: `__int64 __fastcall(char *pv)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d8f0`
- `0x18000e160`

## callees

- `0x18000c820`
- `0x18000ce24`
- `0x18000da20`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dac3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dae7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dae7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000dab1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000dab1`

## string_xrefs

- `0x18000da48`: `CSession::_CreateReaderActionWait`

## pseudocode

```c
__int64 __fastcall CSession::_CreateReaderActionWait(char *pv)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-60h] BYREF
  int v7; // [rsp+24h] [rbp-5Ch] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v9[3]; // [rsp+30h] [rbp-50h] BYREF
  char v10[40]; // [rsp+48h] [rbp-38h] BYREF

  v9[0] = v10;
  v6 = 0;
  v9[1] = &v7;
  v9[2] = &v6;
  v7 = 0;
  strcpy(v10, "CSession::_CreateReaderActionWait");
  lambda_71f3e66b9f666055fa572575827b355a_::operator()(v9);
  v7 = 1;
  v8 = v9;
  ThreadpoolWait = CreateThreadpoolWait(CSession::_HandleReaderAction, pv, (PTP_CALLBACK_ENVIRON)(pv + 440));
  *((_QWORD *)pv + 65) = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)pv + 15), 0);
    v4 = v6;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v6 = v4;
  }
  WppTraceUnwinder__lambda_71f3e66b9f666055fa572575827b355a____::_WppTraceUnwinder__lambda_71f3e66b9f666055fa572575827b355a____(&v8);
  return v4;
}

```

## disassembly

```asm
0x18000da20  mov     [rsp-8+arg_8], rbx
0x18000da25  push    rbp
0x18000da26  mov     rbp, rsp
0x18000da29  sub     rsp, 80h
0x18000da30  mov     rax, cs:__security_cookie
0x18000da37  xor     rax, rsp
0x18000da3a  mov     [rbp+var_10], rax
0x18000da3e  movzx   eax, word ptr cs:aCsessionCreate+20h; "t"
0x18000da45  mov     rbx, rcx
0x18000da48  movups  xmm0, xmmword ptr cs:aCsessionCreate; "CSession::_CreateReaderActionWait"
0x18000da4f  mov     word ptr [rbp+var_38+20h], ax
0x18000da53  lea     rax, [rbp+var_38]
0x18000da57  movups  xmm1, xmmword ptr cs:aCsessionCreate+10h; "eReaderActionWait"
0x18000da5e  mov     [rbp+var_50], rax
0x18000da62  lea     rcx, [rbp+var_50]
0x18000da66  lea     rax, [rbp+var_5C]
0x18000da6a  mov     [rbp+var_60], 0
0x18000da71  mov     [rbp+var_48], rax
0x18000da75  lea     rax, [rbp+var_60]
0x18000da79  mov     [rbp+var_40], rax
0x18000da7d  mov     [rbp+var_5C], 0
0x18000da84  movups  xmmword ptr [rbp+var_38], xmm0
0x18000da88  movups  xmmword ptr [rbp+var_38+10h], xmm1
0x18000da8c  call    _lambda_71f3e66b9f666055fa572575827b355a___operator__
0x18000da91  lea     rax, [rbp+var_50]
0x18000da95  mov     [rbp+var_5C], 1
0x18000da9c  lea     r8, [rbx+1B8h]; pcbe
0x18000daa3  mov     [rbp+var_58], rax
0x18000daa7  mov     rdx, rbx; pv
0x18000daaa  lea     rcx, ?_HandleReaderAction@CSession@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000dab1  call    cs:__imp_CreateThreadpoolWait
0x18000dab7  mov     [rbx+208h], rax
0x18000dabe  test    rax, rax
0x18000dac1  jnz     short loc_18000DADD
0x18000dac3  call    cs:__imp_GetLastError
0x18000dac9  mov     ebx, eax
0x18000dacb  test    eax, eax
0x18000dacd  jle     short loc_18000DAD8
0x18000dacf  movzx   ebx, ax
0x18000dad2  or      ebx, 80070000h
0x18000dad8  mov     [rbp+var_60], ebx
0x18000dadb  jmp     short loc_18000DAF0
0x18000dadd  mov     rdx, [rbx+78h]; h
0x18000dae1  xor     r8d, r8d; pftTimeout
0x18000dae4  mov     rcx, rax; pwa
0x18000dae7  call    cs:__imp_SetThreadpoolWait
0x18000daed  mov     ebx, [rbp+var_60]
0x18000daf0  lea     rcx, [rbp+var_58]
0x18000daf4  call    WppTraceUnwinder__lambda_71f3e66b9f666055fa572575827b355a_______WppTraceUnwinder__lambda_71f3e66b9f666055fa572575827b355a____
0x18000daf9  mov     eax, ebx
0x18000dafb  mov     rcx, [rbp+var_10]
0x18000daff  xor     rcx, rsp; StackCookie
0x18000db02  call    __security_check_cookie
0x18000db07  mov     rbx, [rsp+80h+arg_8]
0x18000db0f  add     rsp, 80h
0x18000db16  pop     rbp
0x18000db17  retn
```
