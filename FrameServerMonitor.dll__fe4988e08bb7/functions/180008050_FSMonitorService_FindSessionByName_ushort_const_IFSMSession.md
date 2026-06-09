# FSMonitorService::FindSessionByName(ushort const *,IFSMSession * *)

- ea: `0x180008050`
- end: `0x18000818f`
- name: `?FindSessionByName@FSMonitorService@@UEAAJPEBGPEAPEAUIFSMSession@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(FSMonitorService *this, const unsigned __int16 *, struct IFSMSession **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x180008050`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000806e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000806e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008176`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800080de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800080de`

## pseudocode

```c
__int64 __fastcall FSMonitorService::FindSessionByName(
        FSMonitorService *this,
        const unsigned __int16 *a2,
        struct IFSMSession **a3)
{
  int v6; // edi
  __int64 v7; // rdx
  unsigned int v8; // r15d
  __int64 i; // rbp
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, struct IFSMSession **); // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 23) == 1 )
  {
    if ( a3 )
    {
      v8 = *((_DWORD *)this + 38);
      v6 = 0;
      *a3 = 0;
      for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
      {
        v10 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
        v11 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
        if ( CompareStringOrdinal(a2, -1, v11, -1, 1) == 2 )
        {
          _mm_lfence();
          v12 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IFSMSession **))(*((_QWORD *)this + 18) + 8 * i);
          v6 = (**v12)(v12, &GUID_d60ca839_2514_4501_b908_a53ae1da522b, a3);
          if ( v6 < 0 )
          {
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_18;
            v7 = 36;
            goto LABEL_17;
          }
          break;
        }
      }
      if ( !*a3 )
      {
        v6 = -1072875819;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 8u )
        {
          v7 = 37;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v6 = -2147467261;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 35;
LABEL_17:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v6);
      }
    }
  }
  else
  {
    v6 = -1072873851;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 34;
      goto LABEL_17;
    }
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008050  push    rbx
0x180008052  push    rbp
0x180008053  push    rsi
0x180008054  push    rdi
0x180008055  push    r12
0x180008057  push    r13
0x180008059  push    r14
0x18000805b  push    r15
0x18000805d  sub     rsp, 38h
0x180008061  mov     rsi, rcx
0x180008064  mov     r14, r8
0x180008067  add     rcx, 30h ; '0'; lpCriticalSection
0x18000806b  mov     r13, rdx
0x18000806e  call    cs:__imp_EnterCriticalSection
0x180008074  cmp     dword ptr [rsi+5Ch], 1
0x180008078  jnz     loc_180008141
0x18000807e  test    r14, r14
0x180008081  jnz     short loc_18000809E
0x180008083  mov     edi, 80004003h
0x180008088  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000808d  cmp     al, 1
0x18000808f  jb      loc_180008172
0x180008095  lea     edx, [r14+23h]
0x180008099  jmp     loc_180008154
0x18000809e  mov     r15d, [rsi+98h]
0x1800080a5  xor     edi, edi
0x1800080a7  mov     [r14], rdi
0x1800080aa  xor     ebp, ebp
0x1800080ac  cmp     ebp, r15d
0x1800080af  jnb     short loc_180008126
0x1800080b1  mov     rax, [rsi+90h]
0x1800080b8  mov     rcx, [rax+rbp*8]
0x1800080bc  mov     rax, [rcx]
0x1800080bf  mov     rax, [rax+20h]
0x1800080c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c8  mov     r8, rax; lpString2
0x1800080cb  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800080d3  or      eax, 0FFFFFFFFh
0x1800080d6  mov     rcx, r13; lpString1
0x1800080d9  mov     r9d, eax; cchCount2
0x1800080dc  mov     edx, eax; cchCount1
0x1800080de  call    cs:__imp_CompareStringOrdinal
0x1800080e4  cmp     eax, 2
0x1800080e7  jz      short loc_1800080ED
0x1800080e9  inc     ebp
0x1800080eb  jmp     short loc_1800080AC
0x1800080ed  lfence
0x1800080f0  mov     rax, [rsi+90h]
0x1800080f7  lea     rdx, _GUID_d60ca839_2514_4501_b908_a53ae1da522b
0x1800080fe  mov     r8, r14
0x180008101  mov     rcx, [rax+rbp*8]
0x180008105  mov     rax, [rcx]
0x180008108  mov     rax, [rax]
0x18000810b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008110  mov     edi, eax
0x180008112  test    eax, eax
0x180008114  jns     short loc_180008126
0x180008116  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000811b  cmp     al, 1
0x18000811d  jb      short loc_180008172
0x18000811f  mov     edx, 24h ; '$'
0x180008124  jmp     short loc_180008154
0x180008126  cmp     qword ptr [r14], 0
0x18000812a  jnz     short loc_180008172
0x18000812c  mov     edi, 0C00D36D5h
0x180008131  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180008136  cmp     al, 8
0x180008138  jb      short loc_180008172
0x18000813a  mov     edx, 25h ; '%'
0x18000813f  jmp     short loc_180008154
0x180008141  mov     edi, 0C00D3E85h
0x180008146  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000814b  cmp     al, 1
0x18000814d  jb      short loc_180008172
0x18000814f  mov     edx, 22h ; '"'
0x180008154  mov     rcx, cs:WPP_GLOBAL_Control
0x18000815b  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008162  mov     r9, rsi
0x180008165  mov     [rsp+78h+bIgnoreCase], edi
0x180008169  mov     rcx, [rcx+10h]
0x18000816d  call    WPP_SF_qD
0x180008172  lea     rcx, [rsi+30h]; lpCriticalSection
0x180008176  call    cs:__imp_LeaveCriticalSection
0x18000817c  mov     eax, edi
0x18000817e  add     rsp, 38h
0x180008182  pop     r15
0x180008184  pop     r14
0x180008186  pop     r13
0x180008188  pop     r12
0x18000818a  pop     rdi
0x18000818b  pop     rsi
0x18000818c  pop     rbp
0x18000818d  pop     rbx
0x18000818e  retn
```
