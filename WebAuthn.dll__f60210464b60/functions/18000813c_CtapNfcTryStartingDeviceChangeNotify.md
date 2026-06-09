# CtapNfcTryStartingDeviceChangeNotify

- ea: `0x18000813c`
- end: `0x180008327`
- name: `CtapNfcTryStartingDeviceChangeNotify`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800080e0`

## callees

- `0x180007f90`
- `0x18000813c`
- `0x180008330`
- `0x18000840c`
- `0x18000a8c0`
- `0x18000ab38`
- `0x1800183ec`
- `0x18002bbf4`
- `0x1800e3d50`
- `0x1800f13c8`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008304`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008304`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000818d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000818d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800081d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800081d3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800081fd`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800081fd`
- `RPCRT4!UuidCreate` at `0x180008170`
- `RPCRT4!UuidCreate` at `0x180008170`

## pseudocode

```c
__int64 CtapNfcTryStartingDeviceChangeNotify()
{
  unsigned int NonzeroLastError; // ebx
  void **i; // rsi
  _QWORD *v2; // rdi
  void **v3; // r14
  _QWORD *v4; // rax
  void *v5; // rcx
  __int64 v6; // rax
  void *v8[2]; // [rsp+20h] [rbp-30h] BYREF
  PVOID pv; // [rsp+30h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-18h] BYREF

  NonzeroLastError = 0;
  Uuid = 0;
  UuidCreate(&Uuid);
  v8[1] = v8;
  v8[0] = v8;
  AcquireSRWLockExclusive(&stru_1801AF270);
  if ( !*((_DWORD *)&hObject + 2) )
  {
    CtapNfcClearDeviceChangeNotifyGlobalState();
    NonzeroLastError = CtapNfcEnumerateReaders((__int64)&Uuid, (__int64)v8);
    if ( !NonzeroLastError && v8[0] != v8 )
    {
      hObject = CreateEventW(0, 0, 0, 0);
      if ( hObject )
      {
        if ( TrySubmitThreadpoolCallback(
               CtapNfcDeviceChangeNotifyManagerCallback,
               &g_DeviceChangeNotifyControlBlockListHead,
               0) )
        {
          for ( i = (void **)v8[0]; ; i = (void **)*i )
          {
            if ( i == v8 )
            {
              *((_DWORD *)&hObject + 2) = 1;
              goto LABEL_18;
            }
            pv = 0;
            if ( !(unsigned int)CtapDeviceCreateControlBlock(i + 2, 0, 0, &pv) )
            {
              v2 = pv;
              v3 = (void **)((char *)pv + 376);
              if ( (unsigned int)CtapNfcCreateContext(i[6]) )
                goto LABEL_13;
              NonzeroLastError = CtapDeviceTrySubmitThreadpoolCallback(CtapNfcDeviceChangeNotifyReaderCallback, v2);
              if ( NonzeroLastError )
              {
                CtapNfcFreeContext(*v3);
LABEL_13:
                CtapDeviceFreeControlBlock(v2);
                continue;
              }
              v4 = g_DeviceChangeNotifyControlBlockListHead;
              if ( *((void ***)g_DeviceChangeNotifyControlBlockListHead + 1) != &g_DeviceChangeNotifyControlBlockListHead )
                goto LABEL_22;
              *v2 = g_DeviceChangeNotifyControlBlockListHead;
              v2[1] = &g_DeviceChangeNotifyControlBlockListHead;
              v4[1] = v2;
              g_DeviceChangeNotifyControlBlockListHead = v2;
            }
          }
        }
        NonzeroLastError = _GetNonzeroLastError();
      }
    }
LABEL_18:
    while ( 1 )
    {
      v5 = v8[0];
      if ( v8[0] == v8 )
        break;
      if ( *((void ***)v8[0] + 1) != v8 || (v6 = *(_QWORD *)v8[0], *(void **)(*(_QWORD *)v8[0] + 8LL) != v8[0]) )
LABEL_22:
        __fastfail(3u);
      v8[0] = *(void **)v8[0];
      *(_QWORD *)(v6 + 8) = v8;
      FidoFree(v5);
    }
    if ( NonzeroLastError )
      CtapNfcClearDeviceChangeNotifyGlobalState();
  }
  ReleaseSRWLockExclusive(&stru_1801AF270);
  return NonzeroLastError;
}

```

## disassembly

```asm
0x18000813c  push    rbp
0x18000813e  push    rbx
0x18000813f  push    rsi
0x180008140  push    rdi
0x180008141  push    r12
0x180008143  push    r14
0x180008145  push    r15
0x180008147  mov     rbp, rsp
0x18000814a  sub     rsp, 50h
0x18000814e  mov     rax, cs:__security_cookie
0x180008155  xor     rax, rsp
0x180008158  mov     [rbp+var_8], rax
0x18000815c  xorps   xmm0, xmm0
0x18000815f  lea     rcx, [rbp+Uuid]; Uuid
0x180008163  xorps   xmm1, xmm1
0x180008166  xor     ebx, ebx
0x180008168  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18000816c  movups  xmmword ptr [rbp+var_30], xmm1
0x180008170  call    cs:__imp_UuidCreate
0x180008176  lea     rax, [rbp+var_30]
0x18000817a  mov     [rbp+var_30+8], rax
0x18000817e  lea     rcx, stru_1801AF270; SRWLock
0x180008185  lea     rax, [rbp+var_30]
0x180008189  mov     [rbp+var_30], rax
0x18000818d  call    cs:__imp_AcquireSRWLockExclusive
0x180008193  cmp     dword ptr cs:hObject+8, ebx
0x180008199  jnz     loc_1800082FD
0x18000819f  call    CtapNfcClearDeviceChangeNotifyGlobalState
0x1800081a4  lea     rdx, [rbp+var_30]
0x1800081a8  lea     rcx, [rbp+Uuid]
0x1800081ac  call    CtapNfcEnumerateReaders
0x1800081b1  mov     ebx, eax
0x1800081b3  test    eax, eax
0x1800081b5  jnz     loc_1800082BA
0x1800081bb  lea     rax, [rbp+var_30]
0x1800081bf  cmp     [rbp+var_30], rax
0x1800081c3  jz      loc_1800082BA
0x1800081c9  xor     r9d, r9d; lpName
0x1800081cc  xor     r8d, r8d; bInitialState
0x1800081cf  xor     edx, edx; bManualReset
0x1800081d1  xor     ecx, ecx; lpEventAttributes
0x1800081d3  call    cs:__imp_CreateEventW
0x1800081d9  mov     qword ptr cs:hObject, rax
0x1800081e0  test    rax, rax
0x1800081e3  jz      loc_1800082BA
0x1800081e9  lea     r12, ?g_DeviceChangeNotifyControlBlockListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceChangeNotifyControlBlockListHead
0x1800081f0  xor     r8d, r8d; pcbe
0x1800081f3  mov     rdx, r12; pv
0x1800081f6  lea     rcx, CtapNfcDeviceChangeNotifyManagerCallback; pfns
0x1800081fd  call    cs:__imp_TrySubmitThreadpoolCallback
0x180008203  test    eax, eax
0x180008205  jz      loc_1800082B3
0x18000820b  mov     rsi, [rbp+var_30]
0x18000820f  jmp     loc_18000829A
0x180008214  lea     r9, [rbp+pv]
0x180008218  mov     [rbp+pv], 0
0x180008220  xor     r8d, r8d
0x180008223  lea     rcx, [rsi+10h]
0x180008227  xor     edx, edx
0x180008229  call    CtapDeviceCreateControlBlock
0x18000822e  test    eax, eax
0x180008230  jnz     short loc_180008297
0x180008232  mov     rdi, [rbp+pv]
0x180008236  lea     r8, [rbp+Uuid]
0x18000823a  mov     rcx, [rsi+30h]; Src
0x18000823e  lea     r14, [rdi+178h]
0x180008245  mov     rdx, r14
0x180008248  call    CtapNfcCreateContext
0x18000824d  test    eax, eax
0x18000824f  jnz     short loc_18000828F
0x180008251  mov     rdx, rdi; pv
0x180008254  lea     rcx, CtapNfcDeviceChangeNotifyReaderCallback; pfns
0x18000825b  call    CtapDeviceTrySubmitThreadpoolCallback
0x180008260  mov     ebx, eax
0x180008262  test    eax, eax
0x180008264  jnz     short loc_180008287
0x180008266  mov     rax, cs:?g_DeviceChangeNotifyControlBlockListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceChangeNotifyControlBlockListHead
0x18000826d  cmp     [rax+8], r12
0x180008271  jnz     short loc_1800082ED
0x180008273  mov     [rdi], rax
0x180008276  mov     [rdi+8], r12
0x18000827a  mov     [rax+8], rdi
0x18000827e  mov     cs:?g_DeviceChangeNotifyControlBlockListHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY g_DeviceChangeNotifyControlBlockListHead
0x180008285  jmp     short loc_180008297
0x180008287  mov     rcx, [r14]; void *
0x18000828a  call    CtapNfcFreeContext
0x18000828f  mov     rcx, rdi; void *
0x180008292  call    CtapDeviceFreeControlBlock
0x180008297  mov     rsi, [rsi]
0x18000829a  lea     rax, [rbp+var_30]
0x18000829e  cmp     rsi, rax
0x1800082a1  jnz     loc_180008214
0x1800082a7  mov     dword ptr cs:hObject+8, 1
0x1800082b1  jmp     short loc_1800082BA
0x1800082b3  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800082b8  mov     ebx, eax
0x1800082ba  mov     rcx, [rbp+var_30]; void *
0x1800082be  lea     rax, [rbp+var_30]
0x1800082c2  cmp     rcx, rax
0x1800082c5  jz      short loc_1800082F4
0x1800082c7  lea     rax, [rbp+var_30]
0x1800082cb  cmp     [rcx+8], rax
0x1800082cf  jnz     short loc_1800082ED
0x1800082d1  mov     rax, [rcx]
0x1800082d4  cmp     [rax+8], rcx
0x1800082d8  jnz     short loc_1800082ED
0x1800082da  lea     rdx, [rbp+var_30]
0x1800082de  mov     [rbp+var_30], rax
0x1800082e2  mov     [rax+8], rdx
0x1800082e6  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800082eb  jmp     short loc_1800082BA
0x1800082ed  mov     ecx, 3
0x1800082f2  int     29h; Win8: RtlFailFast(ecx)
0x1800082f4  test    ebx, ebx
0x1800082f6  jz      short loc_1800082FD
0x1800082f8  call    CtapNfcClearDeviceChangeNotifyGlobalState
0x1800082fd  lea     rcx, stru_1801AF270; SRWLock
0x180008304  call    cs:__imp_ReleaseSRWLockExclusive
0x18000830a  mov     eax, ebx
0x18000830c  mov     rcx, [rbp+var_8]
0x180008310  xor     rcx, rsp; StackCookie
0x180008313  call    __security_check_cookie
0x180008318  add     rsp, 50h
0x18000831c  pop     r15
0x18000831e  pop     r14
0x180008320  pop     r12
0x180008322  pop     rdi
0x180008323  pop     rsi
0x180008324  pop     rbx
0x180008325  pop     rbp
0x180008326  retn
```
