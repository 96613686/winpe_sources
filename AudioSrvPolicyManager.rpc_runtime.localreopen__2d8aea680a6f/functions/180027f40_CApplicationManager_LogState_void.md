# CApplicationManager::LogState(void)

- ea: `0x180027f40`
- end: `0x18002814e`
- name: `?LogState@CApplicationManager@@QEAAXXZ`
- size: `526`
- prototype: `void __fastcall(CApplicationManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800273e0`

## callees

- `0x18001d580`
- `0x180027f40`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028128`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028111`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028111`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CApplicationManager::LogState(CApplicationManager *this)
{
  CApplicationManager *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // r10
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  int v9; // [rsp+30h] [rbp-A9h] BYREF
  int v10; // [rsp+34h] [rbp-A5h] BYREF
  int v11; // [rsp+38h] [rbp-A1h] BYREF
  _DWORD v12[3]; // [rsp+3Ch] [rbp-9Dh] BYREF
  __int64 v13; // [rsp+48h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-79h] BYREF
  void *v16; // [rsp+70h] [rbp-69h]
  int v17; // [rsp+78h] [rbp-61h]
  int v18; // [rsp+7Ch] [rbp-5Dh]
  __int64 *v19; // [rsp+80h] [rbp-59h]
  int v20; // [rsp+88h] [rbp-51h]
  int v21; // [rsp+8Ch] [rbp-4Dh]
  __int64 *v22; // [rsp+90h] [rbp-49h]
  __int64 v23; // [rsp+98h] [rbp-41h]
  _DWORD *v24; // [rsp+A0h] [rbp-39h]
  __int64 v25; // [rsp+A8h] [rbp-31h]
  int *v26; // [rsp+B0h] [rbp-29h]
  __int64 v27; // [rsp+B8h] [rbp-21h]
  int *v28; // [rsp+C0h] [rbp-19h]
  __int64 v29; // [rsp+C8h] [rbp-11h]
  int *v30; // [rsp+D0h] [rbp-9h]
  __int64 v31; // [rsp+D8h] [rbp-1h]

  v1 = g_ApplicationManager;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  v3 = (_QWORD *)*((_QWORD *)v1 + 9);
  while ( v3 )
  {
    v4 = v3[2];
    v3 = (_QWORD *)*v3;
    v5 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 4) != 0 && (*(_QWORD *)(v5 + 24) & 4LL) == *(_QWORD *)(v5 + 24) )
    {
      v9 = -1;
      v10 = -1;
      v11 = -1;
      v12[0] = *(_DWORD *)(v4 + 208) != 0;
      v13 = *(_QWORD *)(v4 + 696);
      v6 = *(__int64 **)(v4 + 24);
      v30 = &v9;
      v31 = 4;
      v28 = &v10;
      v29 = 4;
      v26 = &v11;
      v27 = 4;
      v24 = v12;
      v25 = 4;
      v22 = &v13;
      v23 = 8;
      if ( v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *((_WORD *)v6 + v7) );
        v8 = 2 * v7 + 2;
      }
      else
      {
        v6 = &qword_180053B30;
        v8 = 2;
      }
      v19 = v6;
      v20 = v8;
      v21 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 4;
      UserData.Ptr = *(_QWORD *)(v5 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v16 = &unk_180057838;
      v17 = 123;
      v18 = 1;
      v12[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v5 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180027f40  push    rbp
0x180027f42  push    rbx
0x180027f43  push    rsi
0x180027f44  push    rdi
0x180027f45  push    r12
0x180027f47  push    r13
0x180027f49  push    r14
0x180027f4b  push    r15
0x180027f4d  lea     rbp, [rsp-1Fh]
0x180027f52  sub     rsp, 0F8h
0x180027f59  mov     rax, cs:__security_cookie
0x180027f60  xor     rax, rsp
0x180027f63  mov     [rbp+57h+var_50], rax
0x180027f67  mov     rbx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x180027f6e  lea     rsi, [rbx+20h]
0x180027f72  mov     rcx, rsi; lpCriticalSection
0x180027f75  call    cs:__imp_EnterCriticalSection
0x180027f7b  mov     rbx, [rbx+48h]
0x180027f7f  test    rbx, rbx
0x180027f82  jz      loc_180028120
0x180027f88  xor     r14d, r14d
0x180027f8b  lea     r15, unk_180057838
0x180027f92  lea     r12, _TraceLoggingMetadataEnd
0x180027f99  lea     r13, _TraceLoggingMetadata
0x180027fa0  mov     rdi, [rbx+10h]
0x180027fa4  mov     rbx, [rbx]
0x180027fa7  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180027fac  mov     r10, [rax+8]
0x180027fb0  mov     eax, [r10]
0x180027fb3  cmp     eax, 4
0x180027fb6  jbe     loc_180028117
0x180027fbc  mov     rcx, [r10+18h]
0x180027fc0  mov     rax, [r10+10h]
0x180027fc4  test    al, 4
0x180027fc6  jz      loc_180028117
0x180027fcc  mov     rax, rcx
0x180027fcf  and     eax, 4
0x180027fd2  cmp     rax, rcx
0x180027fd5  jnz     loc_180028117
0x180027fdb  mov     [rsp+130h+var_100], 0FFFFFFFFh
0x180027fe3  mov     [rsp+130h+var_FC], 0FFFFFFFFh
0x180027feb  mov     [rsp+130h+var_F8], 0FFFFFFFFh
0x180027ff3  mov     eax, r14d
0x180027ff6  cmp     [rdi+0D0h], r14d
0x180027ffd  setnz   al
0x180028000  mov     [rsp+130h+var_F4], eax
0x180028004  mov     rax, [rdi+2B8h]
0x18002800b  mov     [rsp+130h+var_E8], rax
0x180028010  mov     rcx, [rdi+18h]
0x180028014  lea     rax, [rsp+130h+var_100]
0x180028019  mov     [rbp+57h+var_60], rax
0x18002801d  mov     [rbp+57h+var_58], 4
0x180028025  lea     rax, [rsp+130h+var_FC]
0x18002802a  mov     [rbp+57h+var_70], rax
0x18002802e  mov     [rbp+57h+var_68], 4
0x180028036  lea     rax, [rsp+130h+var_F8]
0x18002803b  mov     [rbp+57h+var_80], rax
0x18002803f  mov     [rbp+57h+var_78], 4
0x180028047  lea     rax, [rsp+130h+var_F4]
0x18002804c  mov     [rbp+57h+var_90], rax
0x180028050  mov     [rbp+57h+var_88], 4
0x180028058  lea     rax, [rsp+130h+var_E8]
0x18002805d  mov     [rbp+57h+var_A0], rax
0x180028061  mov     [rbp+57h+var_98], 8
0x180028069  test    rcx, rcx
0x18002806c  jz      short loc_180028089
0x18002806e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028075  lea     rax, [rax+1]
0x180028079  cmp     word ptr [rcx+rax*2], 0
0x18002807e  jnz     short loc_180028075
0x180028080  lea     eax, ds:2[rax*2]
0x180028087  jmp     short loc_180028095
0x180028089  lea     rcx, qword_180053B30
0x180028090  mov     eax, 2
0x180028095  mov     [rbp+57h+var_B0], rcx
0x180028099  mov     [rbp+57h+var_A8], eax
0x18002809c  mov     [rbp+57h+var_A4], r14d
0x1800280a0  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x1800280a8  movzx   eax, cs:word_18005782E
0x1800280af  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x1800280b3  mov     [rsp+130h+EventDescriptor.Keyword], 4
0x1800280bc  mov     rax, [r10+8]
0x1800280c0  mov     [rbp+57h+var_D0.Ptr], rax
0x1800280c4  movzx   eax, word ptr [rax]
0x1800280c7  mov     [rbp+57h+var_D0.Size], eax
0x1800280ca  mov     dword ptr [rbp+57h+var_D0.0Ch], 2
0x1800280d1  mov     [rbp+57h+var_C0], r15
0x1800280d5  mov     [rbp+57h+var_B8], 7Bh ; '{'
0x1800280dc  mov     [rbp+57h+var_B4], 1
0x1800280e3  mov     rax, r12
0x1800280e6  sub     eax, r13d
0x1800280e9  mov     [rsp+130h+var_F0], eax
0x1800280ed  mov     eax, [rsp+130h+var_F0]
0x1800280f1  lea     rax, [rbp+57h+var_D0]
0x1800280f5  mov     [rsp+130h+UserData], rax; UserData
0x1800280fa  mov     [rsp+130h+UserDataCount], 8; UserDataCount
0x180028102  xor     r9d, r9d; RelatedActivityId
0x180028105  xor     r8d, r8d; ActivityId
0x180028108  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18002810d  mov     rcx, [r10+20h]; RegHandle
0x180028111  call    cs:__imp_EventWriteTransfer
0x180028117  test    rbx, rbx
0x18002811a  jnz     loc_180027FA0
0x180028120  test    rsi, rsi
0x180028123  jz      short loc_18002812E
0x180028125  mov     rcx, rsi; lpCriticalSection
0x180028128  call    cs:__imp_LeaveCriticalSection
0x18002812e  mov     rcx, [rbp+57h+var_50]
0x180028132  xor     rcx, rsp; StackCookie
0x180028135  call    __security_check_cookie
0x18002813a  add     rsp, 0F8h
0x180028141  pop     r15
0x180028143  pop     r14
0x180028145  pop     r13
0x180028147  pop     r12
0x180028149  pop     rdi
0x18002814a  pop     rsi
0x18002814b  pop     rbx
0x18002814c  pop     rbp
0x18002814d  retn
```
