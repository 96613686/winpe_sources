# _lambda_758cc192c2b6814ec8090745d2a6079d_::operator()(wchar_t const *,wchar_t const *,long)

- ea: `0x1800112f0`
- end: `0x1800114d4`
- name: `??R_lambda_758cc192c2b6814ec8090745d2a6079d_@@QEBA@PEB_W0J@Z`
- size: `484`
- prototype: `int __fastcall(__int64, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800114e0`

## callees

- `0x1800112f0`
- `0x1800116f0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18001136b`
- `KERNEL32!IsDebuggerPresent` at `0x18001136b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800114a2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800114a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall _lambda_758cc192c2b6814ec8090745d2a6079d_::operator()(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        int a4)
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
  const wchar_t *v26; // [rsp+90h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-11h]
  int v28; // [rsp+9Ch] [rbp-Dh]
  const wchar_t *v29; // [rsp+A0h] [rbp-9h]
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
          v11 = a3[++v10] == 0;
        while ( !v11 );
        v12 = 2 * v10 + 2;
      }
      else
      {
        a3 = &S2;
        v12 = 2;
      }
      v29 = a3;
      v30 = v12;
      v31 = 0;
      if ( a2 )
      {
        do
          v11 = a2[++v9] == 0;
        while ( !v11 );
        v13 = 2 * v9 + 2;
      }
      else
      {
        a2 = &S2;
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
      v21 = byte_18002763B;
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
0x1800112f0  mov     [rsp-8+arg_8], rbx
0x1800112f5  mov     [rsp-8+arg_10], rsi
0x1800112fa  push    rbp
0x1800112fb  push    rdi
0x1800112fc  push    r14
0x1800112fe  lea     rbp, [rsp-47h]
0x180011303  sub     rsp, 0F0h
0x18001130a  mov     rax, cs:__security_cookie
0x180011311  xor     rax, rsp
0x180011314  mov     [rbp+57h+var_20], rax
0x180011318  mov     r14d, r9d
0x18001131b  mov     rbx, r8
0x18001131e  mov     rdi, rdx
0x180011321  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180011326  mov     rsi, [rax+8]
0x18001132a  cmp     dword ptr [rsi], 5
0x18001132d  jbe     loc_1800114B0
0x180011333  mov     [rsp+100h+arg_0], r15
0x18001133b  mov     r15, 800000000000h
0x180011345  test    [rsi+10h], r15
0x180011349  jz      loc_1800114A8
0x18001134f  mov     rax, [rsi+18h]
0x180011353  and     rax, r15
0x180011356  cmp     rax, [rsi+18h]
0x18001135a  jnz     loc_1800114A8
0x180011360  mov     [rbp+57h+var_D0], 1
0x180011367  mov     [rbp+57h+var_CC], r14d
0x18001136b  call    cs:__imp_IsDebuggerPresent
0x180011371  xor     edx, edx
0x180011373  mov     [rbp+57h+var_C0], 2000000h
0x18001137b  mov     [rbp+57h+var_C8], eax
0x18001137e  lea     rax, [rbp+57h+var_D0]
0x180011382  mov     [rbp+57h+var_30], rax
0x180011386  lea     rax, [rbp+57h+var_CC]
0x18001138a  mov     [rbp+57h+var_40], rax
0x18001138e  lea     rax, [rbp+57h+var_C8]
0x180011392  mov     [rbp+57h+var_50], rax
0x180011396  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001139d  mov     [rbp+57h+var_28], 4
0x1800113a5  mov     [rbp+57h+var_38], 4
0x1800113ad  mov     [rbp+57h+var_48], 4
0x1800113b5  test    rbx, rbx
0x1800113b8  jz      short loc_1800113D4
0x1800113ba  mov     rcx, rax
0x1800113bd  nop     dword ptr [rax]
0x1800113c0  cmp     [rbx+rcx*2+2], dx
0x1800113c5  lea     rcx, [rcx+1]
0x1800113c9  jnz     short loc_1800113C0
0x1800113cb  lea     ecx, ds:2[rcx*2]
0x1800113d2  jmp     short loc_1800113E0
0x1800113d4  lea     rbx, S2
0x1800113db  mov     ecx, 2
0x1800113e0  mov     [rbp+57h+var_60], rbx
0x1800113e4  mov     [rbp+57h+var_58], ecx
0x1800113e7  mov     [rbp+57h+var_54], edx
0x1800113ea  test    rdi, rdi
0x1800113ed  jz      short loc_180011404
0x1800113ef  nop
0x1800113f0  cmp     [rdi+rax*2+2], dx
0x1800113f5  lea     rax, [rax+1]
0x1800113f9  jnz     short loc_1800113F0
0x1800113fb  lea     eax, ds:2[rax*2]
0x180011402  jmp     short loc_180011410
0x180011404  lea     rdi, S2
0x18001140b  mov     eax, 2
0x180011410  mov     [rbp+57h+var_68], eax
0x180011413  lea     rcx, _TraceLoggingMetadata
0x18001141a  mov     [rbp+57h+var_64], edx
0x18001141d  lea     rax, [rbp+57h+var_C0]
0x180011421  mov     [rbp+57h+var_80], rax
0x180011425  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180011429  movzx   eax, cs:word_180027631
0x180011430  xor     r9d, r9d; RelatedActivityId
0x180011433  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180011436  xor     r8d, r8d; ActivityId
0x180011439  mov     rax, [rsi+8]
0x18001143d  mov     [rbp+57h+var_A0.Ptr], rax
0x180011441  mov     [rbp+57h+var_70], rdi
0x180011445  mov     [rbp+57h+var_78], 8
0x18001144d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180011454  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180011458  movzx   eax, word ptr [rax]
0x18001145b  mov     [rbp+57h+var_A0.Size], eax
0x18001145e  lea     rax, byte_18002763B
0x180011465  mov     [rbp+57h+var_90], rax
0x180011469  lea     rax, _TraceLoggingMetadataEnd
0x180011470  sub     eax, ecx
0x180011472  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x180011479  mov     [rbp+57h+var_88], 68h ; 'h'
0x180011480  mov     [rbp+57h+var_84], 1
0x180011487  mov     [rbp+57h+var_C4], eax
0x18001148a  mov     eax, [rbp+57h+var_C4]
0x18001148d  mov     rcx, [rsi+20h]; RegHandle
0x180011491  lea     rax, [rbp+57h+var_A0]
0x180011495  mov     [rsp+100h+UserData], rax; UserData
0x18001149a  mov     [rsp+100h+UserDataCount], 8; UserDataCount
0x1800114a2  call    cs:__imp_EventWriteTransfer
0x1800114a8  mov     r15, [rsp+100h+arg_0]
0x1800114b0  mov     rcx, [rbp+57h+var_20]
0x1800114b4  xor     rcx, rsp; StackCookie
0x1800114b7  call    __security_check_cookie
0x1800114bc  lea     r11, [rsp+100h+var_10]
0x1800114c4  mov     rbx, [r11+28h]
0x1800114c8  mov     rsi, [r11+30h]
0x1800114cc  mov     rsp, r11
0x1800114cf  pop     r14
0x1800114d1  pop     rdi
0x1800114d2  pop     rbp
0x1800114d3  retn
```
