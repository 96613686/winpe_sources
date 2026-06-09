# BciSetIRTimer(void *,_LARGE_INTEGER *)

- ea: `0x1800085a0`
- end: `0x180008744`
- name: `?BciSetIRTimer@@YAHPEAXPEAT_LARGE_INTEGER@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(void *, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008168`
- `0x18000a474`

## callees

- `0x1800085a0`
- `0x180012dd0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800085dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800085dd`
- `ntdll!NtSetIRTimer` at `0x1800085cc`
- `ntdll!NtSetIRTimer` at `0x1800085cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008719`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008719`

## pseudocode

```c
__int64 __fastcall BciSetIRTimer(void *a1, union _LARGE_INTEGER *a2)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // esi
  DWORD v6; // eax
  unsigned int v7; // ebx
  LONGLONG QuadPart; // rax
  NTSTATUS v10; // [rsp+30h] [rbp-69h] BYREF
  _DWORD v11[3]; // [rsp+34h] [rbp-65h] BYREF
  LONGLONG v12; // [rsp+40h] [rbp-59h] BYREF
  void *v13; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  __int16 *v16; // [rsp+70h] [rbp-29h]
  int v17; // [rsp+78h] [rbp-21h]
  int v18; // [rsp+7Ch] [rbp-1Dh]
  void **v19; // [rsp+80h] [rbp-19h]
  __int64 v20; // [rsp+88h] [rbp-11h]
  _DWORD *v21; // [rsp+90h] [rbp-9h]
  __int64 v22; // [rsp+98h] [rbp-1h]
  NTSTATUS *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]
  LONGLONG *v25; // [rsp+B0h] [rbp+17h]
  __int64 v26; // [rsp+B8h] [rbp+1Fh]

  v4 = NtSetIRTimer();
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = 1;
  }
  else
  {
    v6 = RtlNtStatusToDosError(v4);
    SetLastError(v6);
    v7 = 0;
  }
  if ( dword_180026058 )
  {
    QuadPart = 0;
    if ( a2 )
      QuadPart = a2->QuadPart;
    if ( (unsigned int)dword_180026058 > 5
      && (qword_180026068 & 0x400000000001LL) != 0
      && (qword_180026070 & 0x400000000001LL) == qword_180026070 )
    {
      v12 = QuadPart;
      EventDescriptor.Keyword = 0x400000000001LL;
      v25 = &v12;
      v10 = v5;
      v23 = &v10;
      v11[0] = v7;
      v21 = v11;
      v13 = a1;
      v19 = &v13;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_180026060;
      v26 = 8;
      v24 = 4;
      v22 = 4;
      v20 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_180026060;
      v16 = &word_180020516;
      UserData.Reserved = 2;
      v17 = 64;
      v18 = 1;
      v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800085a0  mov     [rsp-8+arg_10], rbx
0x1800085a5  push    rbp
0x1800085a6  push    rsi
0x1800085a7  push    rdi
0x1800085a8  push    r14
0x1800085aa  push    r15
0x1800085ac  lea     rbp, [rsp-37h]
0x1800085b1  sub     rsp, 0D0h
0x1800085b8  mov     rax, cs:__security_cookie
0x1800085bf  xor     rax, rsp
0x1800085c2  mov     [rbp+57h+var_30], rax
0x1800085c6  mov     rdi, rdx
0x1800085c9  mov     r14, rcx
0x1800085cc  call    cs:__imp_NtSetIRTimer
0x1800085d2  xor     r15d, r15d
0x1800085d5  mov     esi, eax
0x1800085d7  test    eax, eax
0x1800085d9  jns     short loc_1800085F0
0x1800085db  mov     ecx, eax; Status
0x1800085dd  call    cs:__imp_RtlNtStatusToDosError
0x1800085e3  mov     ecx, eax; dwErrCode
0x1800085e5  call    cs:__imp_SetLastError
0x1800085eb  mov     ebx, r15d
0x1800085ee  jmp     short loc_1800085F5
0x1800085f0  mov     ebx, 1
0x1800085f5  mov     eax, cs:dword_180026058
0x1800085fb  test    eax, eax
0x1800085fd  jz      loc_18000871F
0x180008603  mov     rax, r15
0x180008606  test    rdi, rdi
0x180008609  jz      short loc_18000860E
0x18000860b  mov     rax, [rdi]
0x18000860e  mov     ecx, cs:dword_180026058
0x180008614  cmp     ecx, 5
0x180008617  jbe     loc_18000871F
0x18000861d  mov     rdx, cs:qword_180026070
0x180008624  mov     r8, 400000000001h
0x18000862e  mov     rcx, cs:qword_180026068
0x180008635  test    r8, rcx
0x180008638  jz      loc_18000871F
0x18000863e  mov     rcx, rdx
0x180008641  and     rcx, r8
0x180008644  cmp     rcx, rdx
0x180008647  jnz     loc_18000871F
0x18000864d  mov     [rbp+57h+var_B0], rax
0x180008651  lea     rcx, _TraceLoggingMetadataEnd
0x180008658  mov     [rbp+57h+EventDescriptor.Keyword], r8
0x18000865c  lea     rax, [rbp+57h+var_B0]
0x180008660  mov     [rbp+57h+var_40], rax
0x180008664  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180008668  mov     [rbp+57h+var_C0], esi
0x18000866b  lea     rax, [rbp+57h+var_C0]
0x18000866f  mov     [rbp+57h+var_50], rax
0x180008673  xor     r9d, r9d; RelatedActivityId
0x180008676  mov     [rbp+57h+var_BC], ebx
0x180008679  lea     rax, [rbp+57h+var_BC]
0x18000867d  mov     [rbp+57h+var_60], rax
0x180008681  xor     r8d, r8d; ActivityId
0x180008684  lea     rax, [rbp+57h+var_A8]
0x180008688  mov     [rbp+57h+var_A8], r14
0x18000868c  mov     [rbp+57h+var_70], rax
0x180008690  movzx   eax, cs:word_18002050C
0x180008697  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000869a  mov     rax, cs:off_180026060
0x1800086a1  mov     [rbp+57h+var_90.Ptr], rax
0x1800086a5  mov     [rbp+57h+var_38], 8
0x1800086ad  mov     [rbp+57h+var_48], 4
0x1800086b5  mov     [rbp+57h+var_58], 4
0x1800086bd  mov     [rbp+57h+var_68], 8
0x1800086c5  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800086cc  movzx   eax, word ptr [rax]
0x1800086cf  mov     [rbp+57h+var_90.Size], eax
0x1800086d2  lea     rax, word_180020516
0x1800086d9  mov     [rbp+57h+var_80], rax
0x1800086dd  lea     rax, _TraceLoggingMetadata
0x1800086e4  sub     ecx, eax
0x1800086e6  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x1800086ed  mov     [rbp+57h+var_78], 40h ; '@'
0x1800086f4  lea     rax, [rbp+57h+var_90]
0x1800086f8  mov     [rbp+57h+var_74], 1
0x1800086ff  mov     [rbp+57h+var_B8], ecx
0x180008702  mov     ecx, [rbp+57h+var_B8]
0x180008705  mov     rcx, cs:RegHandle; RegHandle
0x18000870c  mov     [rsp+0F0h+UserData], rax; UserData
0x180008711  mov     [rsp+0F0h+UserDataCount], 6; UserDataCount
0x180008719  call    cs:__imp_EventWriteTransfer
0x18000871f  mov     eax, ebx
0x180008721  mov     rcx, [rbp+57h+var_30]
0x180008725  xor     rcx, rsp; StackCookie
0x180008728  call    __security_check_cookie
0x18000872d  mov     rbx, [rsp+0F0h+arg_10]
0x180008735  add     rsp, 0D0h
0x18000873c  pop     r15
0x18000873e  pop     r14
0x180008740  pop     rdi
0x180008741  pop     rsi
0x180008742  pop     rbp
0x180008743  retn
```
