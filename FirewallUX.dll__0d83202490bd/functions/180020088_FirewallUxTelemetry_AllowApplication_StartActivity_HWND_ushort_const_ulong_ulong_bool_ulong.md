# FirewallUxTelemetry::AllowApplication::StartActivity(HWND__ *,ushort const *,ulong,ulong,bool,ulong)

- ea: `0x180020088`
- end: `0x180020285`
- name: `?StartActivity@AllowApplication@FirewallUxTelemetry@@QEAAXPEAUHWND__@@PEBGKK_NK@Z`
- size: `509`
- prototype: `void __fastcall(FirewallUxTelemetry::AllowApplication *__hidden this, HWND, const unsigned __int16 *, unsigned int, unsigned int, bool, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001cdc0`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x18000812c`
- `0x180008820`
- `0x180009fc8`
- `0x180020088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002010a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002010a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800200e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800200e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020142`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::AllowApplication::StartActivity(
        FirewallUxTelemetry::AllowApplication *this,
        HWND a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        bool a6,
        unsigned int a7)
{
  __int64 v11; // rdi
  RTL_SRWLOCK *v12; // rcx
  const struct _tlgProvider_t *v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  const GUID *v16; // r9
  __int64 v17; // rax
  int v18; // eax
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C0h] BYREF
  HWND v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  PSRWLOCK *p_SRWLock; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  HWND *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+BCh] [rbp-44h]
  int *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  unsigned int *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  bool *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  unsigned int *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]

  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v11 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)FirewallUxTraceLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v11 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v11 + 8));
  v12 = SRWLock;
  *(_DWORD *)v11 = 1;
  if ( v12 )
    ReleaseSRWLockExclusive(v12);
  v13 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v13 > 5u )
  {
    v20 = a7;
    v19 = a6;
    v21 = a5;
    v22 = a4;
    v24 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v15 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v25 = 0;
    if ( !*(_BYTE *)(v15 + 4)
      || (v16 = (const GUID *)(v15 + 24), !*(_DWORD *)(v15 + 24))
      && !*(_DWORD *)(v15 + 28)
      && !*(_DWORD *)(v15 + 32)
      && !*(_DWORD *)(v15 + 36) )
    {
      v16 = 0;
    }
    v43 = 4;
    v42 = &v20;
    v40 = &v19;
    v38 = &v21;
    v36 = &v22;
    v41 = 1;
    v39 = 4;
    v37 = 4;
    if ( a3 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      a3 = &szFile;
      v18 = 2;
    }
    v34 = v18;
    v33 = a3;
    v31 = &v24;
    v35 = 0;
    p_SRWLock = &SRWLock;
    v32 = 8;
    v27 = &v25;
    v30 = 4;
    v28 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v13, byte_18003314B, (const GUID *)(v15 + 8), v16, 0xAu, &v26);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirewallUxTelemetry::AllowApplication *)((char *)this + 288));
}

```

## disassembly

```asm
0x180020088  mov     [rsp-8+arg_8], rbx
0x18002008d  mov     [rsp-8+arg_10], rsi
0x180020092  push    rbp
0x180020093  push    rdi
0x180020094  push    r12
0x180020096  push    r14
0x180020098  push    r15
0x18002009a  lea     rbp, [rsp-10h]
0x18002009f  sub     rsp, 110h
0x1800200a6  mov     rax, cs:__security_cookie
0x1800200ad  xor     rax, rsp
0x1800200b0  mov     [rbp+30h+var_30], rax
0x1800200b4  mov     r15, rdx
0x1800200b7  mov     r14d, r9d
0x1800200ba  lea     rdx, [rsp+130h+SRWLock]
0x1800200bf  mov     rbx, r8
0x1800200c2  mov     rsi, rcx
0x1800200c5  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800200ca  mov     rdi, [rsi+110h]
0x1800200d1  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800200d6  mov     r9d, [rax]
0x1800200d9  cmp     r9d, 5
0x1800200dd  jbe     short loc_1800200F0
0x1800200df  lea     rdx, [rdi+8]; ActivityId
0x1800200e3  mov     ecx, 3; ControlCode
0x1800200e8  call    cs:__imp_EventActivityIdControl
0x1800200ee  jmp     short loc_1800200F7
0x1800200f0  xorps   xmm0, xmm0
0x1800200f3  movups  xmmword ptr [rdi+8], xmm0
0x1800200f7  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x1800200fc  xor     r12d, r12d
0x1800200ff  mov     dword ptr [rdi], 1
0x180020105  test    rcx, rcx
0x180020108  jz      short loc_180020110
0x18002010a  call    cs:__imp_ReleaseSRWLockExclusive
0x180020110  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180020115  mov     rdi, rax
0x180020118  mov     ecx, [rax]
0x18002011a  cmp     ecx, 5
0x18002011d  jbe     loc_18002024B
0x180020123  mov     ecx, [rbp+30h+arg_30]
0x180020126  mov     [rsp+130h+var_FC], ecx
0x18002012a  mov     cl, [rbp+30h+arg_28]
0x18002012d  mov     [rsp+130h+var_100], cl
0x180020131  mov     ecx, [rbp+30h+arg_20]
0x180020134  mov     [rsp+130h+var_F8], ecx
0x180020138  mov     [rsp+130h+var_F4], r14d
0x18002013d  mov     [rsp+130h+var_E8], r15
0x180020142  call    cs:__imp_GetCurrentThreadId
0x180020148  mov     r8, [rsi+110h]
0x18002014f  mov     dword ptr [rsp+130h+SRWLock], eax
0x180020153  mov     [rsp+130h+var_E0], r12
0x180020158  cmp     [r8+4], r12b
0x18002015c  jz      short loc_180020179
0x18002015e  lea     r9, [r8+18h]
0x180020162  cmp     [r9], r12d
0x180020165  jnz     short loc_18002017C
0x180020167  cmp     [r9+4], r12d
0x18002016b  jnz     short loc_18002017C
0x18002016d  cmp     [r9+8], r12d
0x180020171  jnz     short loc_18002017C
0x180020173  cmp     [r9+0Ch], r12d
0x180020177  jnz     short loc_18002017C
0x180020179  mov     r9, r12
0x18002017c  mov     [rbp+30h+var_38], 4
0x180020184  lea     rax, [rsp+130h+var_FC]
0x180020189  mov     [rbp+30h+var_40], rax
0x18002018d  lea     rax, [rsp+130h+var_100]
0x180020192  mov     [rbp+30h+var_50], rax
0x180020196  lea     rax, [rsp+130h+var_F8]
0x18002019b  mov     [rbp+30h+var_60], rax
0x18002019f  lea     rax, [rsp+130h+var_F4]
0x1800201a4  mov     [rbp+30h+var_70], rax
0x1800201a8  mov     [rbp+30h+var_48], 1
0x1800201b0  mov     [rbp+30h+var_58], 4
0x1800201b8  mov     [rbp+30h+var_68], 4
0x1800201c0  test    rbx, rbx
0x1800201c3  jz      short loc_1800201DC
0x1800201c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800201c9  inc     rax
0x1800201cc  cmp     [rbx+rax*2], r12w
0x1800201d1  jnz     short loc_1800201C9
0x1800201d3  lea     eax, ds:2[rax*2]
0x1800201da  jmp     short loc_1800201E8
0x1800201dc  lea     rbx, szFile
0x1800201e3  mov     eax, 2
0x1800201e8  mov     [rbp+30h+var_78], eax
0x1800201eb  lea     rdx, byte_18003314B
0x1800201f2  lea     rax, [rsp+130h+var_E8]
0x1800201f7  mov     [rbp+30h+var_80], rbx
0x1800201fb  mov     [rbp+30h+var_90], rax
0x1800201ff  add     r8, 8
0x180020203  lea     rax, [rsp+130h+SRWLock]
0x180020208  mov     [rbp+30h+var_74], r12d
0x18002020c  mov     [rbp+30h+var_A0], rax
0x180020210  mov     rcx, rdi
0x180020213  lea     rax, [rsp+130h+var_E0]
0x180020218  mov     [rbp+30h+var_88], 8
0x180020220  mov     [rbp+30h+var_B0], rax
0x180020224  lea     rax, [rsp+130h+var_D0]
0x180020229  mov     [rsp+130h+var_108], rax
0x18002022e  mov     [rsp+130h+var_110], 0Ah
0x180020236  mov     [rbp+30h+var_98], 4
0x18002023e  mov     [rbp+30h+var_A8], 8
0x180020246  call    _tlgWriteTransfer_EventWriteTransfer
0x18002024b  lea     rcx, [rsi+120h]; this
0x180020252  cmp     [rcx+18h], r12d
0x180020256  jnz     short loc_18002025D
0x180020258  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002025d  mov     rcx, [rbp+30h+var_30]
0x180020261  xor     rcx, rsp; StackCookie
0x180020264  call    __security_check_cookie
0x180020269  lea     r11, [rsp+130h+var_20]
0x180020271  mov     rbx, [r11+38h]
0x180020275  mov     rsi, [r11+40h]
0x180020279  mov     rsp, r11
0x18002027c  pop     r15
0x18002027e  pop     r14
0x180020280  pop     r12
0x180020282  pop     rdi
0x180020283  pop     rbp
0x180020284  retn
```
