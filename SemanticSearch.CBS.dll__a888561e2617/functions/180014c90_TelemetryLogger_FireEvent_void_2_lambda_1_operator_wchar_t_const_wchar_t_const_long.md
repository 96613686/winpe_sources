# `TelemetryLogger::FireEvent_(void)'::`2'::_lambda_1_::operator()(wchar_t const *,wchar_t const *,long)

- ea: `0x180014c90`
- end: `0x180014e74`
- name: `??R_lambda_1_@?1??FireEvent_@TelemetryLogger@@QEAAXXZ@QEBA@PEB_W0J@Z`
- size: `484`
- prototype: `int __fastcall(__int64, __int64 *, __int64 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014e80`

## callees

- `0x180014c90`
- `0x180015090`
- `0x18004c070`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180014d0b`
- `KERNEL32!IsDebuggerPresent` at `0x180014d0b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014e42`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014e42`

## pseudocode

```c
int __fastcall `TelemetryLogger::FireEvent_'::`2'::_lambda_1_::operator()(__int64 a1, __int64 *a2, __int64 *a3, int a4)
{
  struct TelemetryLogger *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rcx
  bool v11; // zf
  int v12; // ecx
  int v13; // eax
  int v15; // [rsp+30h] [rbp-79h] BYREF
  int v16; // [rsp+34h] [rbp-75h] BYREF
  _DWORD v17[2]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v18; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-49h] BYREF
  char *v21; // [rsp+70h] [rbp-39h]
  int v22; // [rsp+78h] [rbp-31h]
  int v23; // [rsp+7Ch] [rbp-2Dh]
  __int64 *v24; // [rsp+80h] [rbp-29h]
  __int64 v25; // [rsp+88h] [rbp-21h]
  __int64 *v26; // [rsp+90h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-11h]
  int v28; // [rsp+9Ch] [rbp-Dh]
  __int64 *v29; // [rsp+A0h] [rbp-9h]
  int v30; // [rsp+A8h] [rbp-1h]
  int v31; // [rsp+ACh] [rbp+3h]
  _DWORD *v32; // [rsp+B0h] [rbp+7h]
  __int64 v33; // [rsp+B8h] [rbp+Fh]
  int *v34; // [rsp+C0h] [rbp+17h]
  __int64 v35; // [rsp+C8h] [rbp+1Fh]
  int *v36; // [rsp+D0h] [rbp+27h]
  __int64 v37; // [rsp+D8h] [rbp+2Fh]

  v7 = TelemetryLogger::Instance();
  v8 = *((_QWORD *)v7 + 1);
  if ( *(_DWORD *)v8 > 5u && (*(_QWORD *)(v8 + 16) & 0x800000000000LL) != 0 )
  {
    v7 = (struct TelemetryLogger *)(*(_QWORD *)(v8 + 24) & 0x800000000000LL);
    if ( v7 == *(struct TelemetryLogger **)(v8 + 24) )
    {
      v15 = 1;
      v16 = a4;
      v18 = 0x2000000;
      v17[0] = IsDebuggerPresent();
      v36 = &v15;
      v34 = &v16;
      v32 = v17;
      v9 = -1;
      v37 = 4;
      v35 = 4;
      v33 = 4;
      if ( a3 )
      {
        v10 = -1;
        do
          v11 = *((_WORD *)a3 + ++v10) == 0;
        while ( !v11 );
        v12 = 2 * v10 + 2;
      }
      else
      {
        a3 = &qword_18006D0D8;
        v12 = 2;
      }
      v29 = a3;
      v30 = v12;
      v31 = 0;
      if ( a2 )
      {
        do
          v11 = *((_WORD *)a2 + ++v9) == 0;
        while ( !v11 );
        v13 = 2 * v9 + 2;
      }
      else
      {
        a2 = &qword_18006D0D8;
        v13 = 2;
      }
      v27 = v13;
      v28 = 0;
      v24 = &v18;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v8 + 8);
      v26 = a2;
      v25 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x800000000000LL;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v21 = byte_1800793EB;
      UserData.Reserved = 2;
      v22 = 104;
      v23 = 1;
      v17[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      LODWORD(v7) = EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
    }
  }
  return (int)v7;
}

```

## disassembly

```asm
0x180014c90  mov     [rsp-8+arg_8], rbx
0x180014c95  mov     [rsp-8+arg_10], rsi
0x180014c9a  push    rbp
0x180014c9b  push    rdi
0x180014c9c  push    r14
0x180014c9e  lea     rbp, [rsp-47h]
0x180014ca3  sub     rsp, 0F0h
0x180014caa  mov     rax, cs:__security_cookie
0x180014cb1  xor     rax, rsp
0x180014cb4  mov     [rbp+57h+var_20], rax
0x180014cb8  mov     r14d, r9d
0x180014cbb  mov     rbx, r8
0x180014cbe  mov     rdi, rdx
0x180014cc1  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180014cc6  mov     rsi, [rax+8]
0x180014cca  cmp     dword ptr [rsi], 5
0x180014ccd  jbe     loc_180014E50
0x180014cd3  mov     [rsp+100h+arg_0], r15
0x180014cdb  mov     r15, 800000000000h
0x180014ce5  test    [rsi+10h], r15
0x180014ce9  jz      loc_180014E48
0x180014cef  mov     rax, [rsi+18h]
0x180014cf3  and     rax, r15
0x180014cf6  cmp     rax, [rsi+18h]
0x180014cfa  jnz     loc_180014E48
0x180014d00  mov     [rbp+57h+var_D0], 1
0x180014d07  mov     [rbp+57h+var_CC], r14d
0x180014d0b  call    cs:__imp_IsDebuggerPresent
0x180014d11  xor     edx, edx
0x180014d13  mov     [rbp+57h+var_C0], 2000000h
0x180014d1b  mov     [rbp+57h+var_C8], eax
0x180014d1e  lea     rax, [rbp+57h+var_D0]
0x180014d22  mov     [rbp+57h+var_30], rax
0x180014d26  lea     rax, [rbp+57h+var_CC]
0x180014d2a  mov     [rbp+57h+var_40], rax
0x180014d2e  lea     rax, [rbp+57h+var_C8]
0x180014d32  mov     [rbp+57h+var_50], rax
0x180014d36  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014d3d  mov     [rbp+57h+var_28], 4
0x180014d45  mov     [rbp+57h+var_38], 4
0x180014d4d  mov     [rbp+57h+var_48], 4
0x180014d55  test    rbx, rbx
0x180014d58  jz      short loc_180014D74
0x180014d5a  mov     rcx, rax
0x180014d5d  nop     dword ptr [rax]
0x180014d60  cmp     [rbx+rcx*2+2], dx
0x180014d65  lea     rcx, [rcx+1]
0x180014d69  jnz     short loc_180014D60
0x180014d6b  lea     ecx, ds:2[rcx*2]
0x180014d72  jmp     short loc_180014D80
0x180014d74  lea     rbx, qword_18006D0D8
0x180014d7b  mov     ecx, 2
0x180014d80  mov     [rbp+57h+var_60], rbx
0x180014d84  mov     [rbp+57h+var_58], ecx
0x180014d87  mov     [rbp+57h+var_54], edx
0x180014d8a  test    rdi, rdi
0x180014d8d  jz      short loc_180014DA4
0x180014d8f  nop
0x180014d90  cmp     [rdi+rax*2+2], dx
0x180014d95  lea     rax, [rax+1]
0x180014d99  jnz     short loc_180014D90
0x180014d9b  lea     eax, ds:2[rax*2]
0x180014da2  jmp     short loc_180014DB0
0x180014da4  lea     rdi, qword_18006D0D8
0x180014dab  mov     eax, 2
0x180014db0  mov     [rbp+57h+var_68], eax
0x180014db3  lea     rcx, _TraceLoggingMetadata
0x180014dba  mov     [rbp+57h+var_64], edx
0x180014dbd  lea     rax, [rbp+57h+var_C0]
0x180014dc1  mov     [rbp+57h+var_80], rax
0x180014dc5  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180014dc9  movzx   eax, cs:word_1800793E1
0x180014dd0  xor     r9d, r9d; RelatedActivityId
0x180014dd3  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180014dd6  xor     r8d, r8d; ActivityId
0x180014dd9  mov     rax, [rsi+8]
0x180014ddd  mov     [rbp+57h+var_A0.Ptr], rax
0x180014de1  mov     [rbp+57h+var_70], rdi
0x180014de5  mov     [rbp+57h+var_78], 8
0x180014ded  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180014df4  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180014df8  movzx   eax, word ptr [rax]
0x180014dfb  mov     [rbp+57h+var_A0.Size], eax
0x180014dfe  lea     rax, byte_1800793EB
0x180014e05  mov     [rbp+57h+var_90], rax
0x180014e09  lea     rax, _TraceLoggingMetadataEnd
0x180014e10  sub     eax, ecx
0x180014e12  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x180014e19  mov     [rbp+57h+var_88], 68h ; 'h'
0x180014e20  mov     [rbp+57h+var_84], 1
0x180014e27  mov     [rbp+57h+var_C4], eax
0x180014e2a  mov     eax, [rbp+57h+var_C4]
0x180014e2d  mov     rcx, [rsi+20h]; RegHandle
0x180014e31  lea     rax, [rbp+57h+var_A0]
0x180014e35  mov     [rsp+100h+UserData], rax; UserData
0x180014e3a  mov     [rsp+100h+UserDataCount], 8; UserDataCount
0x180014e42  call    cs:__imp_EventWriteTransfer
0x180014e48  mov     r15, [rsp+100h+arg_0]
0x180014e50  mov     rcx, [rbp+57h+var_20]
0x180014e54  xor     rcx, rsp; StackCookie
0x180014e57  call    __security_check_cookie
0x180014e5c  lea     r11, [rsp+100h+var_10]
0x180014e64  mov     rbx, [r11+28h]
0x180014e68  mov     rsi, [r11+30h]
0x180014e6c  mov     rsp, r11
0x180014e6f  pop     r14
0x180014e71  pop     rdi
0x180014e72  pop     rbp
0x180014e73  retn
```
