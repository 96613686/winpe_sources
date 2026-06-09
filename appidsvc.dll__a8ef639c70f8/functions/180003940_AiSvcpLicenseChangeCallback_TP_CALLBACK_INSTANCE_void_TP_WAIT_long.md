# AiSvcpLicenseChangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180003940`
- end: `0x1800039d8`
- name: `?AiSvcpLicenseChangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `152`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800037d8`
- `0x180003940`
- `0x180003bd0`
- `0x1800049a8`
- `0x180008838`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800039d1`

## pseudocode

```c
void __fastcall AiSvcpLicenseChangeCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids,
      "AiSvcpLicenseChangeCallback");
  v4 = AiSvcpSrpEnabled;
  if ( (int)AiLicReadIntegerValue(&qword_18000ECF0) >= 0 )
  {
    v5 = AiSvcpSrpEnabled;
  }
  else
  {
    v5 = 1;
    AiSvcpSrpEnabled = 1;
  }
  if ( v4 != v5 )
  {
    if ( v5 )
      AiSvcpInitializeGpCallback();
    else
      AiSvcpUninitializeGpCallback();
  }
  SetThreadpoolWait(AiSvcpLicenseChangeWaitObject, AiSvcpLicenseChangeEvent, 0);
}

```

## disassembly

```asm
0x180003940  push    rbx
0x180003942  sub     rsp, 20h
0x180003946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000394d  lea     rax, WPP_GLOBAL_Control
0x180003954  cmp     rcx, rax
0x180003957  jz      short loc_18000397E
0x180003959  test    dword ptr [rcx+1Ch], 400h
0x180003960  jz      short loc_18000397E
0x180003962  mov     rcx, [rcx+10h]
0x180003966  lea     r9, aAisvcplicensec; "AiSvcpLicenseChangeCallback"
0x18000396d  mov     edx, 39h ; '9'
0x180003972  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x180003979  call    WPP_SF_s
0x18000397e  mov     ebx, cs:?AiSvcpSrpEnabled@@3KA; ulong AiSvcpSrpEnabled
0x180003984  lea     rcx, qword_18000ECF0
0x18000398b  call    AiLicReadIntegerValue
0x180003990  test    eax, eax
0x180003992  jns     short loc_1800039A1
0x180003994  mov     eax, 1
0x180003999  mov     cs:?AiSvcpSrpEnabled@@3KA, eax; ulong AiSvcpSrpEnabled
0x18000399f  jmp     short loc_1800039A7
0x1800039a1  mov     eax, cs:?AiSvcpSrpEnabled@@3KA; ulong AiSvcpSrpEnabled
0x1800039a7  cmp     ebx, eax
0x1800039a9  jz      short loc_1800039BB
0x1800039ab  test    eax, eax
0x1800039ad  jz      short loc_1800039B6
0x1800039af  call    ?AiSvcpInitializeGpCallback@@YAKXZ; AiSvcpInitializeGpCallback(void)
0x1800039b4  jmp     short loc_1800039BB
0x1800039b6  call    ?AiSvcpUninitializeGpCallback@@YAXXZ; AiSvcpUninitializeGpCallback(void)
0x1800039bb  mov     rdx, cs:?AiSvcpLicenseChangeEvent@@3PEAXEA; void * AiSvcpLicenseChangeEvent
0x1800039c2  xor     r8d, r8d
0x1800039c5  mov     rcx, cs:?AiSvcpLicenseChangeWaitObject@@3PEAU_TP_WAIT@@EA; _TP_WAIT * AiSvcpLicenseChangeWaitObject
0x1800039cc  add     rsp, 20h
0x1800039d0  pop     rbx
0x1800039d1  jmp     cs:__imp_SetThreadpoolWait
```
