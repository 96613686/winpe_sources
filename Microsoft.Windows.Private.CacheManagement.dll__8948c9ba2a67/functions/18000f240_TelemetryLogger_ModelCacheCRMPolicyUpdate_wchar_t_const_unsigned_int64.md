# TelemetryLogger::ModelCacheCRMPolicyUpdate_(wchar_t const *,unsigned __int64)

- ea: `0x18000f240`
- end: `0x18000f3a9`
- name: `?ModelCacheCRMPolicyUpdate_@TelemetryLogger@@QEAAXPEB_W_K@Z`
- size: `361`
- prototype: `void __fastcall(TelemetryLogger *this, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180007ef0`

## callees

- `0x18000f240`
- `0x1800116f0`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f382`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f382`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::ModelCacheCRMPolicyUpdate_(TelemetryLogger *this, const wchar_t *a2, __int64 a3)
{
  __int64 v5; // r10
  __int64 v6; // rax
  int v8; // eax
  __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  __int64 v10; // [rsp+40h] [rbp-29h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-9h] BYREF
  char *v13; // [rsp+70h] [rbp+7h]
  int v14; // [rsp+78h] [rbp+Fh]
  int v15; // [rsp+7Ch] [rbp+13h]
  const wchar_t *v16; // [rsp+80h] [rbp+17h]
  int v17; // [rsp+88h] [rbp+1Fh]
  int v18; // [rsp+8Ch] [rbp+23h]
  __int64 *v19; // [rsp+90h] [rbp+27h]
  __int64 v20; // [rsp+98h] [rbp+2Fh]
  __int64 *v21; // [rsp+A0h] [rbp+37h]
  __int64 v22; // [rsp+A8h] [rbp+3Fh]

  v5 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u
    && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
  {
    v9 = 0x1000000;
    v21 = &v9;
    v10 = a3;
    v19 = &v10;
    v22 = 8;
    v20 = 8;
    if ( a2 )
    {
      v6 = -1;
      while ( a2[++v6] != 0 )
        ;
      v8 = 2 * v6 + 2;
    }
    else
    {
      a2 = &S2;
      v8 = 2;
    }
    v17 = v8;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v5 + 8);
    v18 = 0;
    EventDescriptor.Keyword = 0x400000000000LL;
    v16 = a2;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v13 = &byte_180027057;
    UserData.Reserved = 2;
    v14 = 79;
    v15 = 1;
    EventWriteTransfer(*(_QWORD *)(v5 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
  }
}

```

## disassembly

```asm
0x18000f240  mov     [rsp-8+arg_0], rbx
0x18000f245  mov     [rsp-8+arg_8], rdi
0x18000f24a  push    rbp
0x18000f24b  lea     rbp, [rsp-57h]
0x18000f250  sub     rsp, 0C0h
0x18000f257  mov     rax, cs:__security_cookie
0x18000f25e  xor     rax, rsp
0x18000f261  mov     [rbp+57h+var_10], rax
0x18000f265  mov     rdi, r8
0x18000f268  mov     rbx, rdx
0x18000f26b  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000f270  mov     r10, [rax+8]
0x18000f274  cmp     dword ptr [r10], 5
0x18000f278  jbe     loc_18000F388
0x18000f27e  mov     rdx, 400000000000h
0x18000f288  test    [r10+10h], rdx
0x18000f28c  jz      loc_18000F388
0x18000f292  mov     rax, [r10+18h]
0x18000f296  and     rax, rdx
0x18000f299  cmp     rax, [r10+18h]
0x18000f29d  jnz     loc_18000F388
0x18000f2a3  lea     rax, [rbp+57h+var_88]
0x18000f2a7  mov     [rbp+57h+var_88], 1000000h
0x18000f2af  mov     [rbp+57h+var_20], rax
0x18000f2b3  xor     ecx, ecx
0x18000f2b5  mov     [rbp+57h+var_80], rdi
0x18000f2b9  lea     rax, [rbp+57h+var_80]
0x18000f2bd  mov     [rbp+57h+var_30], rax
0x18000f2c1  mov     [rbp+57h+var_18], 8
0x18000f2c9  mov     [rbp+57h+var_28], 8
0x18000f2d1  test    rbx, rbx
0x18000f2d4  jz      short loc_18000F2F4
0x18000f2d6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f2dd  nop     dword ptr [rax]
0x18000f2e0  cmp     [rbx+rax*2+2], cx
0x18000f2e5  lea     rax, [rax+1]
0x18000f2e9  jnz     short loc_18000F2E0
0x18000f2eb  lea     eax, ds:2[rax*2]
0x18000f2f2  jmp     short loc_18000F300
0x18000f2f4  lea     rbx, S2
0x18000f2fb  mov     eax, 2
0x18000f300  mov     [rbp+57h+var_38], eax
0x18000f303  xor     r9d, r9d; RelatedActivityId
0x18000f306  movzx   eax, cs:word_18002704D
0x18000f30d  xor     r8d, r8d; ActivityId
0x18000f310  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000f313  mov     rax, [r10+8]
0x18000f317  mov     [rbp+57h+var_60.Ptr], rax
0x18000f31b  mov     [rbp+57h+var_34], ecx
0x18000f31e  lea     rcx, _TraceLoggingMetadata
0x18000f325  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x18000f329  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000f32d  mov     [rbp+57h+var_40], rbx
0x18000f331  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000f338  movzx   eax, word ptr [rax]
0x18000f33b  mov     [rbp+57h+var_60.Size], eax
0x18000f33e  lea     rax, byte_180027057
0x18000f345  mov     [rbp+57h+var_50], rax
0x18000f349  lea     rax, _TraceLoggingMetadataEnd
0x18000f350  sub     eax, ecx
0x18000f352  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18000f359  mov     [rbp+57h+var_48], 4Fh ; 'O'
0x18000f360  mov     [rbp+57h+var_44], 1
0x18000f367  mov     [rbp+57h+var_90], eax
0x18000f36a  mov     eax, [rbp+57h+var_90]
0x18000f36d  mov     rcx, [r10+20h]; RegHandle
0x18000f371  lea     rax, [rbp+57h+var_60]
0x18000f375  mov     [rsp+0C0h+UserData], rax; UserData
0x18000f37a  mov     [rsp+0C0h+UserDataCount], 5; UserDataCount
0x18000f382  call    cs:__imp_EventWriteTransfer
0x18000f388  mov     rcx, [rbp+57h+var_10]
0x18000f38c  xor     rcx, rsp; StackCookie
0x18000f38f  call    __security_check_cookie
0x18000f394  lea     r11, [rsp+0C0h+var_s0]
0x18000f39c  mov     rbx, [r11+10h]
0x18000f3a0  mov     rdi, [r11+18h]
0x18000f3a4  mov     rsp, r11
0x18000f3a7  pop     rbp
0x18000f3a8  retn
```
