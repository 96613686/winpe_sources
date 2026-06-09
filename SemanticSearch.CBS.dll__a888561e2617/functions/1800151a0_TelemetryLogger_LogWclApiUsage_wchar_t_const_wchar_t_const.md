# TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)

- ea: `0x1800151a0`
- end: `0x180015375`
- name: `?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z`
- size: `469`
- prototype: `void __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `42`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0d0`
- `0x18000a440`
- `0x18000a5b0`
- `0x18000ae40`
- `0x18000b2a0`
- `0x18000ba70`
- `0x18000bba0`
- `0x18000bdd0`
- `0x180017080`
- `0x180017600`
- `0x180017760`
- `0x180018550`
- `0x18001b880`
- `0x18001bb90`
- `0x18001bfc0`
- `0x18001c120`
- `0x18001cc80`
- `0x180033980`
- `0x180033af0`
- `0x180033e10`
- `0x180034290`
- `0x180034b20`
- `0x180034c70`
- `0x180034f70`
- `0x18003f9f0`
- `0x18003fb50`
- `0x1800406a0`
- `0x180051770`
- `0x180051d80`
- `0x180052120`
- `0x1800524e0`
- `0x1800528b0`
- `0x180052c90`
- `0x180053610`
- `0x180053fa0`
- `0x180054370`
- `0x1800583b0`
- `0x180058d60`
- `0x180059130`
- `0x180059520`
- `0x180059980`
- `0x18005bc90`

## callees

- `0x180015090`
- `0x1800151a0`
- `0x18004c070`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180015216`
- `KERNEL32!IsDebuggerPresent` at `0x180015216`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015342`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015342`

## pseudocode

```c
void __fastcall TelemetryLogger::LogWclApiUsage(const wchar_t *a1, const wchar_t *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rcx
  bool v7; // zf
  int v8; // ecx
  int v9; // eax
  int v10; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v11[3]; // [rsp+34h] [rbp-55h] BYREF
  __int64 v12; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v15; // [rsp+70h] [rbp-19h]
  int v16; // [rsp+78h] [rbp-11h]
  int v17; // [rsp+7Ch] [rbp-Dh]
  __int64 *v18; // [rsp+80h] [rbp-9h]
  __int64 v19; // [rsp+88h] [rbp-1h]
  const wchar_t *v20; // [rsp+90h] [rbp+7h]
  int v21; // [rsp+98h] [rbp+Fh]
  int v22; // [rsp+9Ch] [rbp+13h]
  const wchar_t *v23; // [rsp+A0h] [rbp+17h]
  int v24; // [rsp+A8h] [rbp+1Fh]
  int v25; // [rsp+ACh] [rbp+23h]
  _DWORD *v26; // [rsp+B0h] [rbp+27h]
  __int64 v27; // [rsp+B8h] [rbp+2Fh]
  int *v28; // [rsp+C0h] [rbp+37h]
  __int64 v29; // [rsp+C8h] [rbp+3Fh]

  v4 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u
    && (*(_QWORD *)(v4 + 16) & 0x800000000000LL) != 0
    && (*(_QWORD *)(v4 + 24) & 0x800000000000LL) == *(_QWORD *)(v4 + 24) )
  {
    v10 = 1;
    v12 = 0x2000000;
    v11[0] = IsDebuggerPresent();
    v28 = &v10;
    v26 = v11;
    v5 = -1;
    v29 = 4;
    v27 = 4;
    if ( a2 )
    {
      v6 = -1;
      do
        v7 = a2[++v6] == 0;
      while ( !v7 );
      v8 = 2 * v6 + 2;
    }
    else
    {
      a2 = (const wchar_t *)&qword_18006D0D8;
      v8 = 2;
    }
    v23 = a2;
    v24 = v8;
    v25 = 0;
    if ( a1 )
    {
      do
        v7 = a1[++v5] == 0;
      while ( !v7 );
      v9 = 2 * v5 + 2;
    }
    else
    {
      a1 = (const wchar_t *)&qword_18006D0D8;
      v9 = 2;
    }
    v21 = v9;
    v22 = 0;
    v18 = &v12;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v4 + 8);
    v20 = a1;
    v19 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x800000000000LL;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v15 = &byte_18007945F;
    UserData.Reserved = 2;
    v16 = 97;
    v17 = 1;
    v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v4 + 32), &EventDescriptor, 0, 0, 7u, &UserData);
  }
}

```

## disassembly

```asm
0x1800151a0  mov     [rsp-8+arg_8], rbx
0x1800151a5  mov     [rsp-8+arg_10], rsi
0x1800151aa  mov     [rsp-8+arg_18], rdi
0x1800151af  push    rbp
0x1800151b0  lea     rbp, [rsp-57h]
0x1800151b5  sub     rsp, 0E0h
0x1800151bc  mov     rax, cs:__security_cookie
0x1800151c3  xor     rax, rsp
0x1800151c6  mov     [rbp+57h+var_10], rax
0x1800151ca  mov     rbx, rdx
0x1800151cd  mov     rdi, rcx
0x1800151d0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800151d5  mov     rsi, [rax+8]
0x1800151d9  cmp     dword ptr [rsi], 5
0x1800151dc  jbe     loc_180015350
0x1800151e2  mov     [rsp+0E0h+arg_0], r14
0x1800151ea  mov     r14, 800000000000h
0x1800151f4  test    [rsi+10h], r14
0x1800151f8  jz      loc_180015348
0x1800151fe  mov     rax, [rsi+18h]
0x180015202  and     rax, r14
0x180015205  cmp     rax, [rsi+18h]
0x180015209  jnz     loc_180015348
0x18001520f  mov     [rbp+57h+var_B0], 1
0x180015216  call    cs:__imp_IsDebuggerPresent
0x18001521c  xor     edx, edx
0x18001521e  mov     [rbp+57h+var_A0], 2000000h
0x180015226  mov     [rbp+57h+var_AC], eax
0x180015229  lea     rax, [rbp+57h+var_B0]
0x18001522d  mov     [rbp+57h+var_20], rax
0x180015231  lea     rax, [rbp+57h+var_AC]
0x180015235  mov     [rbp+57h+var_30], rax
0x180015239  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180015240  mov     [rbp+57h+var_18], 4
0x180015248  mov     [rbp+57h+var_28], 4
0x180015250  test    rbx, rbx
0x180015253  jz      short loc_180015274
0x180015255  mov     rcx, rax
0x180015258  nop     dword ptr [rax+rax+00000000h]
0x180015260  cmp     [rbx+rcx*2+2], dx
0x180015265  lea     rcx, [rcx+1]
0x180015269  jnz     short loc_180015260
0x18001526b  lea     ecx, ds:2[rcx*2]
0x180015272  jmp     short loc_180015280
0x180015274  lea     rbx, qword_18006D0D8
0x18001527b  mov     ecx, 2
0x180015280  mov     [rbp+57h+var_40], rbx
0x180015284  mov     [rbp+57h+var_38], ecx
0x180015287  mov     [rbp+57h+var_34], edx
0x18001528a  test    rdi, rdi
0x18001528d  jz      short loc_1800152A4
0x18001528f  nop
0x180015290  cmp     [rdi+rax*2+2], dx
0x180015295  lea     rax, [rax+1]
0x180015299  jnz     short loc_180015290
0x18001529b  lea     eax, ds:2[rax*2]
0x1800152a2  jmp     short loc_1800152B0
0x1800152a4  lea     rdi, qword_18006D0D8
0x1800152ab  mov     eax, 2
0x1800152b0  mov     [rbp+57h+var_48], eax
0x1800152b3  lea     rcx, _TraceLoggingMetadata
0x1800152ba  mov     [rbp+57h+var_44], edx
0x1800152bd  lea     rax, [rbp+57h+var_A0]
0x1800152c1  mov     [rbp+57h+var_60], rax
0x1800152c5  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800152c9  movzx   eax, cs:word_180079455
0x1800152d0  xor     r9d, r9d; RelatedActivityId
0x1800152d3  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800152d6  xor     r8d, r8d; ActivityId
0x1800152d9  mov     rax, [rsi+8]
0x1800152dd  mov     [rbp+57h+var_80.Ptr], rax
0x1800152e1  mov     [rbp+57h+var_50], rdi
0x1800152e5  mov     [rbp+57h+var_58], 8
0x1800152ed  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800152f4  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x1800152f8  movzx   eax, word ptr [rax]
0x1800152fb  mov     [rbp+57h+var_80.Size], eax
0x1800152fe  lea     rax, byte_18007945F
0x180015305  mov     [rbp+57h+var_70], rax
0x180015309  lea     rax, _TraceLoggingMetadataEnd
0x180015310  sub     eax, ecx
0x180015312  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180015319  mov     [rbp+57h+var_68], 61h ; 'a'
0x180015320  mov     [rbp+57h+var_64], 1
0x180015327  mov     [rbp+57h+var_A8], eax
0x18001532a  mov     eax, [rbp+57h+var_A8]
0x18001532d  mov     rcx, [rsi+20h]; RegHandle
0x180015331  lea     rax, [rbp+57h+var_80]
0x180015335  mov     [rsp+0E0h+UserData], rax; UserData
0x18001533a  mov     [rsp+0E0h+UserDataCount], 7; UserDataCount
0x180015342  call    cs:__imp_EventWriteTransfer
0x180015348  mov     r14, [rsp+0E0h+arg_0]
0x180015350  mov     rcx, [rbp+57h+var_10]
0x180015354  xor     rcx, rsp; StackCookie
0x180015357  call    __security_check_cookie
0x18001535c  lea     r11, [rsp+0E0h+var_s0]
0x180015364  mov     rbx, [r11+18h]
0x180015368  mov     rsi, [r11+20h]
0x18001536c  mov     rdi, [r11+28h]
0x180015370  mov     rsp, r11
0x180015373  pop     rbp
0x180015374  retn
```
