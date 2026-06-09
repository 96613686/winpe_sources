# HandleStopPoolOptimizationRequest(TASK_STOP_POOL_OPTIMIZATION_REQUEST const *)

- ea: `0x1400188b0`
- end: `0x1400189a4`
- name: `?HandleStopPoolOptimizationRequest@@YAHPEBUTASK_STOP_POOL_OPTIMIZATION_REQUEST@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(const struct TASK_STOP_POOL_OPTIMIZATION_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x140015524`
- `0x14001832c`
- `0x1400188b0`
- `0x14001ed86`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SleepEx` at `0x140018984`
- `KERNEL32!SleepEx` at `0x140018984`
- `KERNEL32!DeviceIoControl` at `0x140018962`
- `KERNEL32!DeviceIoControl` at `0x140018962`

## pseudocode

```c
__int64 __fastcall HandleStopPoolOptimizationRequest(const struct TASK_STOP_POOL_OPTIMIZATION_REQUEST *a1)
{
  struct _GUID *v1; // rbx
  __int64 result; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  struct _GUID v4; // [rsp+48h] [rbp-40h] BYREF
  __int128 InBuffer; // [rsp+58h] [rbp-30h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp-20h] BYREF

  v1 = (struct _GUID *)((char *)a1 + 16);
  Buf1 = 0;
  InBuffer = *((_OWORD *)a1 + 1);
  result = IssueProgressStringResult(32906);
  if ( (_DWORD)result )
  {
    if ( (unsigned int)SuGetRebalanceTaskId(v1, &Buf1) )
    {
      if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u)
        || (BytesReturned = 0, DeviceIoControl(Spaceport, 0xE7CC0Cu, &InBuffer, 0x20u, 0, 0, &BytesReturned, 0)) )
      {
        while ( !(unsigned int)SuGetRebalanceTaskId(v1, &v4) )
          SleepEx(0x3E8u, 0);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400188b0  push    rbx
0x1400188b2  sub     rsp, 80h
0x1400188b9  mov     rax, cs:__security_cookie
0x1400188c0  xor     rax, rsp
0x1400188c3  mov     [rsp+88h+var_10], rax
0x1400188c8  xorps   xmm0, xmm0
0x1400188cb  lea     rbx, [rcx+10h]
0x1400188cf  movups  [rsp+88h+Buf1], xmm0
0x1400188d4  mov     ecx, 808Ah
0x1400188d9  movups  xmm0, xmmword ptr [rbx]
0x1400188dc  movdqu  [rsp+88h+InBuffer], xmm0
0x1400188e2  call    IssueProgressStringResult
0x1400188e7  test    eax, eax
0x1400188e9  jz      loc_14001898E
0x1400188ef  lea     rdx, [rsp+88h+Buf1]; struct _GUID *
0x1400188f4  mov     rcx, rbx; struct _GUID *
0x1400188f7  call    ?SuGetRebalanceTaskId@@YAHPEAU_GUID@@0@Z; SuGetRebalanceTaskId(_GUID *,_GUID *)
0x1400188fc  test    eax, eax
0x1400188fe  jz      loc_14001898C
0x140018904  mov     r8d, 10h; Size
0x14001890a  lea     rdx, GUID_NULL; Buf2
0x140018911  lea     rcx, [rsp+88h+Buf1]; Buf1
0x140018916  call    memcmp_0
0x14001891b  test    eax, eax
0x14001891d  jz      short loc_14001896C
0x14001891f  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140018926  lea     rax, [rsp+88h+BytesReturned]
0x14001892b  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x140018934  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x140018939  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x14001893e  mov     r9d, 20h ; ' '; nInBufferSize
0x140018944  mov     [rsp+88h+nOutBufferSize], 0; nOutBufferSize
0x14001894c  mov     edx, 0E7CC0Ch; dwIoControlCode
0x140018951  mov     [rsp+88h+lpOutBuffer], 0; lpOutBuffer
0x14001895a  mov     [rsp+88h+BytesReturned], 0
0x140018962  call    cs:__imp_DeviceIoControl
0x140018968  test    eax, eax
0x14001896a  jz      short loc_14001898C
0x14001896c  lea     rdx, [rsp+88h+var_40]; struct _GUID *
0x140018971  mov     rcx, rbx; struct _GUID *
0x140018974  call    ?SuGetRebalanceTaskId@@YAHPEAU_GUID@@0@Z; SuGetRebalanceTaskId(_GUID *,_GUID *)
0x140018979  test    eax, eax
0x14001897b  jnz     short loc_14001898C
0x14001897d  xor     edx, edx; bAlertable
0x14001897f  mov     ecx, 3E8h; dwMilliseconds
0x140018984  call    cs:__imp_SleepEx
0x14001898a  jmp     short loc_14001896C
0x14001898c  xor     eax, eax
0x14001898e  mov     rcx, [rsp+88h+var_10]
0x140018993  xor     rcx, rsp; StackCookie
0x140018996  call    __security_check_cookie
0x14001899b  add     rsp, 80h
0x1400189a2  pop     rbx
0x1400189a3  retn
```
