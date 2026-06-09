# _lambda_758cc192c2b6814ec8090745d2a6079d_::operator()(wchar_t const *,wchar_t const *,long)

- ea: `0x18002fa90`
- end: `0x18002fc74`
- name: `??R_lambda_758cc192c2b6814ec8090745d2a6079d_@@QEBA@PEB_W0J@Z`
- size: `484`
- prototype: `int __fastcall(__int64, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180030540`

## callees

- `0x18002f6a0`
- `0x18002fa90`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18002fb0b`
- `KERNEL32!IsDebuggerPresent` at `0x18002fb0b`
- `ADVAPI32!EventWriteTransfer` at `0x18002fc42`
- `ADVAPI32!EventWriteTransfer` at `0x18002fc42`

## pseudocode

```c
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
  int *v21; // [rsp+70h] [rbp-39h]
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
        a3 = &Src;
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
        a2 = &Src;
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
      v21 = &dword_18004DB74;
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
0x18002fa90  mov     [rsp-8+arg_8], rbx
0x18002fa95  mov     [rsp-8+arg_10], rsi
0x18002fa9a  push    rbp
0x18002fa9b  push    rdi
0x18002fa9c  push    r14
0x18002fa9e  lea     rbp, [rsp-47h]
0x18002faa3  sub     rsp, 0F0h
0x18002faaa  mov     rax, cs:__security_cookie
0x18002fab1  xor     rax, rsp
0x18002fab4  mov     [rbp+57h+var_20], rax
0x18002fab8  mov     r14d, r9d
0x18002fabb  mov     rbx, r8
0x18002fabe  mov     rdi, rdx
0x18002fac1  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18002fac6  mov     rsi, [rax+8]
0x18002faca  cmp     dword ptr [rsi], 5
0x18002facd  jbe     loc_18002FC50
0x18002fad3  mov     [rsp+100h+arg_0], r15
0x18002fadb  mov     r15, 800000000000h
0x18002fae5  test    [rsi+10h], r15
0x18002fae9  jz      loc_18002FC48
0x18002faef  mov     rax, [rsi+18h]
0x18002faf3  and     rax, r15
0x18002faf6  cmp     rax, [rsi+18h]
0x18002fafa  jnz     loc_18002FC48
0x18002fb00  mov     [rbp+57h+var_D0], 1
0x18002fb07  mov     [rbp+57h+var_CC], r14d
0x18002fb0b  call    cs:__imp_IsDebuggerPresent
0x18002fb11  xor     edx, edx
0x18002fb13  mov     [rbp+57h+var_C0], 2000000h
0x18002fb1b  mov     [rbp+57h+var_C8], eax
0x18002fb1e  lea     rax, [rbp+57h+var_D0]
0x18002fb22  mov     [rbp+57h+var_30], rax
0x18002fb26  lea     rax, [rbp+57h+var_CC]
0x18002fb2a  mov     [rbp+57h+var_40], rax
0x18002fb2e  lea     rax, [rbp+57h+var_C8]
0x18002fb32  mov     [rbp+57h+var_50], rax
0x18002fb36  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002fb3d  mov     [rbp+57h+var_28], 4
0x18002fb45  mov     [rbp+57h+var_38], 4
0x18002fb4d  mov     [rbp+57h+var_48], 4
0x18002fb55  test    rbx, rbx
0x18002fb58  jz      short loc_18002FB74
0x18002fb5a  mov     rcx, rax
0x18002fb5d  nop     dword ptr [rax]
0x18002fb60  cmp     [rbx+rcx*2+2], dx
0x18002fb65  lea     rcx, [rcx+1]
0x18002fb69  jnz     short loc_18002FB60
0x18002fb6b  lea     ecx, ds:2[rcx*2]
0x18002fb72  jmp     short loc_18002FB80
0x18002fb74  lea     rbx, Src
0x18002fb7b  mov     ecx, 2
0x18002fb80  mov     [rbp+57h+var_60], rbx
0x18002fb84  mov     [rbp+57h+var_58], ecx
0x18002fb87  mov     [rbp+57h+var_54], edx
0x18002fb8a  test    rdi, rdi
0x18002fb8d  jz      short loc_18002FBA4
0x18002fb8f  nop
0x18002fb90  cmp     [rdi+rax*2+2], dx
0x18002fb95  lea     rax, [rax+1]
0x18002fb99  jnz     short loc_18002FB90
0x18002fb9b  lea     eax, ds:2[rax*2]
0x18002fba2  jmp     short loc_18002FBB0
0x18002fba4  lea     rdi, Src
0x18002fbab  mov     eax, 2
0x18002fbb0  mov     [rbp+57h+var_68], eax
0x18002fbb3  lea     rcx, _TraceLoggingMetadata
0x18002fbba  mov     [rbp+57h+var_64], edx
0x18002fbbd  lea     rax, [rbp+57h+var_C0]
0x18002fbc1  mov     [rbp+57h+var_80], rax
0x18002fbc5  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002fbc9  movzx   eax, cs:word_18004DB6A
0x18002fbd0  xor     r9d, r9d; RelatedActivityId
0x18002fbd3  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002fbd6  xor     r8d, r8d; ActivityId
0x18002fbd9  mov     rax, [rsi+8]
0x18002fbdd  mov     [rbp+57h+var_A0.Ptr], rax
0x18002fbe1  mov     [rbp+57h+var_70], rdi
0x18002fbe5  mov     [rbp+57h+var_78], 8
0x18002fbed  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002fbf4  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18002fbf8  movzx   eax, word ptr [rax]
0x18002fbfb  mov     [rbp+57h+var_A0.Size], eax
0x18002fbfe  lea     rax, dword_18004DB74
0x18002fc05  mov     [rbp+57h+var_90], rax
0x18002fc09  lea     rax, _TraceLoggingMetadataEnd
0x18002fc10  sub     eax, ecx
0x18002fc12  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x18002fc19  mov     [rbp+57h+var_88], 68h ; 'h'
0x18002fc20  mov     [rbp+57h+var_84], 1
0x18002fc27  mov     [rbp+57h+var_C4], eax
0x18002fc2a  mov     eax, [rbp+57h+var_C4]
0x18002fc2d  mov     rcx, [rsi+20h]; RegHandle
0x18002fc31  lea     rax, [rbp+57h+var_A0]
0x18002fc35  mov     [rsp+100h+UserData], rax; UserData
0x18002fc3a  mov     [rsp+100h+UserDataCount], 8; UserDataCount
0x18002fc42  call    cs:__imp_EventWriteTransfer
0x18002fc48  mov     r15, [rsp+100h+arg_0]
0x18002fc50  mov     rcx, [rbp+57h+var_20]
0x18002fc54  xor     rcx, rsp; StackCookie
0x18002fc57  call    __security_check_cookie
0x18002fc5c  lea     r11, [rsp+100h+var_10]
0x18002fc64  mov     rbx, [r11+28h]
0x18002fc68  mov     rsi, [r11+30h]
0x18002fc6c  mov     rsp, r11
0x18002fc6f  pop     r14
0x18002fc71  pop     rdi
0x18002fc72  pop     rbp
0x18002fc73  retn
```
