# CTranscodeMetadataHelper::FillMetadataStreamIDMap(CTBucketHash<ulong,StreamSinkInfo> &,STREAMID_MAP *,ulong,ulong *)

- ea: `0x180015e7c`
- end: `0x180015fe1`
- name: `?FillMetadataStreamIDMap@CTranscodeMetadataHelper@@CAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@PEAUSTREAMID_MAP@@KPEAK@Z`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180038188`
- `0x180038368`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000ee40`
- `0x180015e7c`
- `0x18001a330`
- `0x18001c280`
- `0x180038114`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015f26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015f26`

## pseudocode

```c
__int64 __fastcall CTranscodeMetadataHelper::FillMetadataStreamIDMap(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4)
{
  unsigned int v6; // edi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  unsigned int v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+90h] [rbp+30h] BYREF

  v17 = 0;
  *a4 = 0;
  v6 = 1;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)CTBucketHash<unsigned long,StreamSinkInfo>::GetFirstPosition(a1, &v15) )
  {
    while ( (unsigned int)CTBucketHash<unsigned long,StreamSinkInfo>::GetNext(a1, &v15, &v17, &v16) )
    {
      if ( v6 >= 3 )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v17,
          "CTranscodeMetadataHelper::FillMetadataStreamIDMap",
          104);
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
        v11 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v10 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeMetadataHelper::FillMetadataStreamIDMap",
              104,
              -2147418113);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids,
            0,
            -2147418113);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
        return v11;
      }
      v8 = v6++;
      *(_DWORD *)(a2 + 8 * v8) = v17;
      *(_DWORD *)(a2 + 8 * v8 + 4) = v16;
    }
  }
  v11 = 0;
  *a4 = v6;
  return v11;
}

```

## disassembly

```asm
0x180015e7c  mov     [rsp-18h+arg_0], rbx
0x180015e81  mov     [rsp-18h+arg_8], rsi
0x180015e86  mov     [rsp-18h+arg_10], r8d
0x180015e8b  push    rbp
0x180015e8c  push    rdi
0x180015e8d  push    r14
0x180015e8f  mov     rbp, rsp
0x180015e92  sub     rsp, 60h
0x180015e96  xor     eax, eax
0x180015e98  mov     rbx, rdx
0x180015e9b  xorps   xmm0, xmm0
0x180015e9e  mov     [rbp+arg_10], eax
0x180015ea1  xorps   xmm1, xmm1
0x180015ea4  mov     [r9], eax
0x180015ea7  lea     rdx, [rbp+var_30]
0x180015eab  mov     rsi, r9
0x180015eae  lea     edi, [rax+1]
0x180015eb1  mov     r14, rcx
0x180015eb4  movups  [rbp+var_30], xmm0
0x180015eb8  movups  [rbp+var_20], xmm1
0x180015ebc  call    ?GetFirstPosition@?$CTBucketHash@KUStreamSinkInfo@@@@QEAAHAEAU_POSITION@1@@Z; CTBucketHash<ulong,StreamSinkInfo>::GetFirstPosition(CTBucketHash<ulong,StreamSinkInfo>::_POSITION &)
0x180015ec1  test    eax, eax
0x180015ec3  jz      loc_180015FC6
0x180015ec9  lea     r9, [rbp+var_20]
0x180015ecd  mov     rcx, r14
0x180015ed0  lea     r8, [rbp+arg_10]
0x180015ed4  lea     rdx, [rbp+var_30]
0x180015ed8  call    ?GetNext@?$CTBucketHash@KUStreamSinkInfo@@@@QEAAHAEAU_POSITION@1@AEAKAEAUStreamSinkInfo@@@Z; CTBucketHash<ulong,StreamSinkInfo>::GetNext(CTBucketHash<ulong,StreamSinkInfo>::_POSITION &,ulong &,StreamSinkInfo &)
0x180015edd  test    eax, eax
0x180015edf  jz      loc_180015FC6
0x180015ee5  cmp     edi, 3
0x180015ee8  jnb     short loc_180015EFD
0x180015eea  mov     eax, [rbp+arg_10]
0x180015eed  mov     ecx, edi
0x180015eef  inc     edi
0x180015ef1  mov     [rbx+rcx*8], eax
0x180015ef4  mov     eax, dword ptr [rbp+var_20]
0x180015ef7  mov     [rbx+rcx*8+4], eax
0x180015efb  jmp     short loc_180015EC9
0x180015efd  mov     edi, 68h ; 'h'
0x180015f02  lea     rdx, aCtranscodemeta_0; "CTranscodeMetadataHelper::FillMetadataS"...
0x180015f09  mov     r8d, edi; int
0x180015f0c  lea     rcx, [rbp+arg_10]; this
0x180015f10  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015f15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015f1c  mov     ebx, 8000FFFFh
0x180015f21  test    rcx, rcx
0x180015f24  jnz     short loc_180015F67
0x180015f26  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015f2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015f33  mov     rcx, rax
0x180015f36  test    rax, rax
0x180015f39  jz      short loc_180015F59
0x180015f3b  mov     rax, [rax]
0x180015f3e  mov     edx, 7F0h
0x180015f43  mov     rax, [rax+8]
0x180015f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f4c  test    eax, eax
0x180015f4e  jz      short loc_180015F59
0x180015f50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015f57  jmp     short loc_180015F67
0x180015f59  lea     rcx, qword_180069A90; this
0x180015f60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015f67  cmp     byte ptr [rcx+8], 0
0x180015f6b  jz      short loc_180015F8F
0x180015f6d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015f72  cmp     [rax+7CCh], ebx
0x180015f78  jz      short loc_180015F8F
0x180015f7a  mov     r9d, ebx; int
0x180015f7d  lea     rdx, aCtranscodemeta_0; "CTranscodeMetadataHelper::FillMetadataS"...
0x180015f84  mov     r8d, edi; int
0x180015f87  mov     rcx, rax; this
0x180015f8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015f8f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180015f94  cmp     al, 1
0x180015f96  jb      short loc_180015FBB
0x180015f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f9f  lea     r8, WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids
0x180015fa6  mov     edx, 14h
0x180015fab  mov     [rsp+60h+var_40], ebx
0x180015faf  xor     r9d, r9d
0x180015fb2  mov     rcx, [rcx+10h]
0x180015fb6  call    WPP_SF_qd
0x180015fbb  lea     rcx, [rbp+arg_10]; this
0x180015fbf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015fc4  jmp     short loc_180015FCA
0x180015fc6  xor     ebx, ebx
0x180015fc8  mov     [rsi], edi
0x180015fca  lea     r11, [rsp+60h+var_s0]
0x180015fcf  mov     eax, ebx
0x180015fd1  mov     rbx, [r11+20h]
0x180015fd5  mov     rsi, [r11+28h]
0x180015fd9  mov     rsp, r11
0x180015fdc  pop     r14
0x180015fde  pop     rdi
0x180015fdf  pop     rbp
0x180015fe0  retn
```
