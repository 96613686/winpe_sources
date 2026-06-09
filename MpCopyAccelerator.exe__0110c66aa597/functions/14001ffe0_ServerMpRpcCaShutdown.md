# ServerMpRpcCaShutdown

- ea: `0x14001ffe0`
- end: `0x14002021f`
- name: `ServerMpRpcCaShutdown`
- size: `575`
- prototype: `signed int __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14001da4c`
- `0x14001da70`
- `0x14001ffe0`
- `0x140020748`
- `0x140022a08`
- `0x14002380c`
- `0x140024148`
- `0x1400241f8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400200f1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140020129`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400200f1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140020129`
- `KERNEL32!SetEvent` at `0x1400200d9`
- `KERNEL32!SetEvent` at `0x140020196`
- `KERNEL32!SetEvent` at `0x1400200d9`
- `KERNEL32!SetEvent` at `0x140020196`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140020116`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140020183`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140020116`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140020183`
- `KERNEL32!GetLastError` at `0x1400201a0`
- `KERNEL32!GetLastError` at `0x1400201a0`

## string_xrefs

- `0x140020091`: `Tampering attempt: MpCopyAccelerator is attempted to be shutdown by non-authorized application, access denied.\n`
- `0x14002015f`: `MpCopyAccelerator completed wait for in-progress copy operations during shutdown.\n`
- `0x1400201db`: `MpCopyAccelerator successfully shutdown.\n`
- `0x1400201f2`: `MpCopyAccelerator will not be signalled to shutdown.\n`

## pseudocode

```c
signed int __fastcall ServerMpRpcCaShutdown(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned int v4; // ecx
  int v5; // eax
  int v6; // ebx
  signed int result; // eax
  HANDLE *Instance; // rbx
  RTL_SRWLOCK *v9; // rbx
  __int64 ***Ptr; // rcx
  __int64 **i; // rax
  int v12[10]; // [rsp+20h] [rbp-28h] BYREF

  *a3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, a2);
  MpCmdLogPrintf(L"Shutdown requested, flags:%lu (0x%lX)\n", a2, a2);
  if ( !dword_14003DB98 )
  {
    v12[0] = 0;
    v5 = CheckRpcClientIdentity(v4, v12);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
          (unsigned int)v5);
      return v6;
    }
    if ( !v12[0] )
    {
      MpCmdLogPrintf(
        L"Tampering attempt: MpCopyAccelerator is attempted to be shutdown by non-authorized application, access denied.\n");
      return -2147024891;
    }
  }
  Instance = (HANDLE *)CCopyControl::GetInstance();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_30f9c55aabed343523773b84d16d3470_Traceguids);
  SetEvent(*Instance);
  if ( (a2 & 1) != 0 )
  {
    v9 = (RTL_SRWLOCK *)CCopyControl::GetInstance();
    AcquireSRWLockExclusive(v9 + 3);
    Ptr = (__int64 ***)v9[1].Ptr;
    for ( i = *Ptr; i != (__int64 **)Ptr; i = (__int64 **)*i )
      *(_DWORD *)i[2] = 1;
    ReleaseSRWLockExclusive(v9 + 3);
  }
  if ( (a2 & 2) != 0 )
  {
    AcquireSRWLockExclusive(&stru_14003DBA0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    if ( dword_14003DB98 )
    {
      MpCmdLogWithTimePrintf(L"MpCopyAccelerator completed wait for in-progress copy operations during shutdown.\n");
      if ( qword_14003DBC8 )
        CLogHandle::Flush(qword_14003DBC8);
    }
    ReleaseSRWLockExclusive(&stru_14003DBA0);
  }
  if ( (a2 & 4) != 0 )
  {
    if ( dword_14003DB98 )
    {
      MpCmdLogWithTimePrintf(L"MpCopyAccelerator will not be signalled to shutdown.\n");
      if ( qword_14003DBC8 )
        CLogHandle::Flush(qword_14003DBC8);
    }
    return 0;
  }
  if ( SetEvent(g_hShutdownEvent) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    MpCmdLogPrintf(L"MpCopyAccelerator successfully shutdown.\n");
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001ffe0  mov     [rsp+arg_0], rbx
0x14001ffe5  push    rsi
0x14001ffe6  push    rdi
0x14001ffe7  push    r14
0x14001ffe9  sub     rsp, 30h
0x14001ffed  mov     edi, edx
0x14001ffef  mov     dword ptr [r8], 0
0x14001fff6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fffd  lea     r14, WPP_GLOBAL_Control
0x140020004  cmp     rcx, r14
0x140020007  jz      short loc_140020027
0x140020009  test    byte ptr [rcx+1Ch], 4
0x14002000d  jz      short loc_140020027
0x14002000f  mov     rcx, [rcx+10h]
0x140020013  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14002001a  mov     edx, 2Ah ; '*'
0x14002001f  mov     r9d, edi
0x140020022  call    WPP_SF_d
0x140020027  mov     r8d, edi
0x14002002a  lea     rcx, aShutdownReques; "Shutdown requested, flags:%lu (0x%lX)\n"
0x140020031  mov     edx, edi
0x140020033  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x140020038  cmp     cs:dword_14003DB98, 0
0x14002003f  jnz     short loc_1400200A7
0x140020041  lea     rdx, [rsp+48h+var_28]; int *
0x140020046  mov     [rsp+48h+var_28], 0
0x14002004e  call    ?CheckRpcClientIdentity@@YAJKPEAH@Z; CheckRpcClientIdentity(ulong,int *)
0x140020053  mov     ebx, eax
0x140020055  test    eax, eax
0x140020057  jns     short loc_14002008A
0x140020059  mov     rcx, cs:WPP_GLOBAL_Control
0x140020060  cmp     rcx, r14
0x140020063  jz      short loc_140020083
0x140020065  test    byte ptr [rcx+1Ch], 1
0x140020069  jz      short loc_140020083
0x14002006b  mov     rcx, [rcx+10h]
0x14002006f  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x140020076  mov     edx, 2Bh ; '+'
0x14002007b  mov     r9d, eax
0x14002007e  call    WPP_SF_d
0x140020083  mov     eax, ebx
0x140020085  jmp     loc_140020211
0x14002008a  cmp     [rsp+48h+var_28], 0
0x14002008f  jnz     short loc_1400200A7
0x140020091  lea     rcx, aTamperingAttem_0; "Tampering attempt: MpCopyAccelerator is"...
0x140020098  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14002009d  mov     eax, 80070005h
0x1400200a2  jmp     loc_140020211
0x1400200a7  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x1400200ac  mov     rbx, rax
0x1400200af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400200b6  cmp     rcx, r14
0x1400200b9  jz      short loc_1400200D6
0x1400200bb  test    byte ptr [rcx+1Ch], 4
0x1400200bf  jz      short loc_1400200D6
0x1400200c1  mov     rcx, [rcx+10h]
0x1400200c5  lea     r8, WPP_30f9c55aabed343523773b84d16d3470_Traceguids
0x1400200cc  mov     edx, 0Eh
0x1400200d1  call    WPP_SF_
0x1400200d6  mov     rcx, [rbx]; hEvent
0x1400200d9  call    cs:__imp_SetEvent
0x1400200df  test    dil, 1
0x1400200e3  jz      short loc_14002011C
0x1400200e5  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x1400200ea  mov     rbx, rax
0x1400200ed  lea     rcx, [rax+18h]; SRWLock
0x1400200f1  call    cs:__imp_AcquireSRWLockExclusive
0x1400200f7  mov     rcx, [rbx+8]
0x1400200fb  mov     rax, [rcx]
0x1400200fe  cmp     rax, rcx
0x140020101  jz      short loc_140020112
0x140020103  mov     rdx, [rax+10h]
0x140020107  mov     dword ptr [rdx], 1
0x14002010d  mov     rax, [rax]
0x140020110  jmp     short loc_1400200FE
0x140020112  lea     rcx, [rbx+18h]; SRWLock
0x140020116  call    cs:__imp_ReleaseSRWLockExclusive
0x14002011c  test    dil, 2
0x140020120  jz      short loc_140020189
0x140020122  lea     rcx, stru_14003DBA0; SRWLock
0x140020129  call    cs:__imp_AcquireSRWLockExclusive
0x14002012f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020136  cmp     rcx, r14
0x140020139  jz      short loc_140020156
0x14002013b  test    byte ptr [rcx+1Ch], 4
0x14002013f  jz      short loc_140020156
0x140020141  mov     rcx, [rcx+10h]
0x140020145  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14002014c  mov     edx, 2Ch ; ','
0x140020151  call    WPP_SF_
0x140020156  cmp     cs:dword_14003DB98, 0
0x14002015d  jz      short loc_14002017C
0x14002015f  lea     rcx, aMpcopyaccelera_2; "MpCopyAccelerator completed wait for in"...
0x140020166  call    ?MpCmdLogWithTimePrintf@@YAXPEB_WZZ; MpCmdLogWithTimePrintf(wchar_t const *,...)
0x14002016b  mov     rcx, cs:qword_14003DBC8; this
0x140020172  test    rcx, rcx
0x140020175  jz      short loc_14002017C
0x140020177  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14002017c  lea     rcx, stru_14003DBA0; SRWLock
0x140020183  call    cs:__imp_ReleaseSRWLockExclusive
0x140020189  test    dil, 4
0x14002018d  jnz     short loc_1400201E9
0x14002018f  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hEvent
0x140020196  call    cs:__imp_SetEvent
0x14002019c  test    eax, eax
0x14002019e  jnz     short loc_1400201B4
0x1400201a0  call    cs:__imp_GetLastError
0x1400201a6  test    eax, eax
0x1400201a8  jle     short loc_140020211
0x1400201aa  movzx   eax, ax
0x1400201ad  or      eax, 80070000h
0x1400201b2  jmp     short loc_140020211
0x1400201b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201bb  cmp     rcx, r14
0x1400201be  jz      short loc_1400201DB
0x1400201c0  test    byte ptr [rcx+1Ch], 4
0x1400201c4  jz      short loc_1400201DB
0x1400201c6  mov     rcx, [rcx+10h]
0x1400201ca  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x1400201d1  mov     edx, 2Dh ; '-'
0x1400201d6  call    WPP_SF_
0x1400201db  lea     rcx, aMpcopyaccelera; "MpCopyAccelerator successfully shutdown"...
0x1400201e2  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x1400201e7  jmp     short loc_14002020F
0x1400201e9  cmp     cs:dword_14003DB98, 0
0x1400201f0  jz      short loc_14002020F
0x1400201f2  lea     rcx, aMpcopyaccelera_4; "MpCopyAccelerator will not be signalled"...
0x1400201f9  call    ?MpCmdLogWithTimePrintf@@YAXPEB_WZZ; MpCmdLogWithTimePrintf(wchar_t const *,...)
0x1400201fe  mov     rcx, cs:qword_14003DBC8; this
0x140020205  test    rcx, rcx
0x140020208  jz      short loc_14002020F
0x14002020a  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14002020f  xor     eax, eax
0x140020211  mov     rbx, [rsp+48h+arg_0]
0x140020216  add     rsp, 30h
0x14002021a  pop     r14
0x14002021c  pop     rdi
0x14002021d  pop     rsi
0x14002021e  retn
```
