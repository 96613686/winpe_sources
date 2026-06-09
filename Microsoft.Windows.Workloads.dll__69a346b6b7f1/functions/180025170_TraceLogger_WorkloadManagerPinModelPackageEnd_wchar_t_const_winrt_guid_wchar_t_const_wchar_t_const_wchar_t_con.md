# TraceLogger::WorkloadManagerPinModelPackageEnd<wchar_t const *,winrt::guid &,wchar_t const *,wchar_t const *>(wchar_t const * &&,winrt::guid &,wchar_t const * &&,wchar_t const * &&)

- ea: `0x180025170`
- end: `0x180025331`
- name: `??$WorkloadManagerPinModelPackageEnd@PEB_WAEAUguid@winrt@@PEB_WPEB_W@TraceLogger@@SAX$$QEAPEB_WAEAUguid@winrt@@00@Z`
- size: `449`
- prototype: `int __fastcall(const wchar_t **, __int128 *, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023c50`

## callees

- `0x1800119b0`
- `0x180025170`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180025302`
- `ADVAPI32!EventWriteTransfer` at `0x180025302`

## pseudocode

```c
int __fastcall TraceLogger::WorkloadManagerPinModelPackageEnd<wchar_t const *,winrt::guid &,wchar_t const *,wchar_t const *>(
        const wchar_t **a1,
        __int128 *a2,
        const wchar_t **a3,
        const wchar_t **a4)
{
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // r10
  const wchar_t *v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // r8
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  bool v15; // zf
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // eax
  __int128 v21; // [rsp+38h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  __int16 *v24; // [rsp+70h] [rbp-9h]
  int v25; // [rsp+78h] [rbp-1h]
  int v26; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v27; // [rsp+80h] [rbp+7h]
  int v28; // [rsp+88h] [rbp+Fh]
  int v29; // [rsp+8Ch] [rbp+13h]
  __int128 *v30; // [rsp+90h] [rbp+17h]
  __int64 v31; // [rsp+98h] [rbp+1Fh]
  const wchar_t *v32; // [rsp+A0h] [rbp+27h]
  int v33; // [rsp+A8h] [rbp+2Fh]
  int v34; // [rsp+ACh] [rbp+33h]
  const wchar_t *v35; // [rsp+B0h] [rbp+37h]
  int v36; // [rsp+B8h] [rbp+3Fh]
  int v37; // [rsp+BCh] [rbp+43h]

  v8 = TraceLogger::Provider();
  v9 = v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    v10 = *a4;
    v11 = -1;
    v12 = *a3;
    v13 = *a1;
    v21 = *a2;
    if ( v10 )
    {
      v14 = -1;
      do
        v15 = v10[++v14] == 0;
      while ( !v15 );
      v16 = 2 * v14 + 2;
    }
    else
    {
      v10 = &Src;
      v16 = 2;
    }
    v35 = v10;
    v36 = v16;
    v37 = 0;
    if ( v12 )
    {
      v17 = -1;
      do
        v15 = v12[++v17] == 0;
      while ( !v15 );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v12 = &Src;
      v18 = 2;
    }
    v33 = v18;
    v30 = &v21;
    v32 = v12;
    v34 = 0;
    v31 = 16;
    if ( v13 )
    {
      do
        v15 = v13[++v11] == 0;
      while ( !v15 );
      v19 = 2 * v11 + 2;
    }
    else
    {
      v13 = &Src;
      v19 = 2;
    }
    v28 = v19;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *((_QWORD *)v9 + 1);
    v27 = v13;
    v29 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v24 = word_18004D412;
    UserData.Reserved = 2;
    v25 = 92;
    v26 = 1;
    LODWORD(v8) = EventWriteTransfer(*((_QWORD *)v9 + 4), &EventDescriptor, 0, 0, 6u, &UserData);
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180025170  mov     [rsp-8+arg_0], rbx
0x180025175  mov     [rsp-8+arg_8], rsi
0x18002517a  mov     [rsp-8+arg_10], rdi
0x18002517f  mov     [rsp-8+arg_18], r14
0x180025184  push    rbp
0x180025185  lea     rbp, [rsp-57h]
0x18002518a  sub     rsp, 0D0h
0x180025191  mov     rax, cs:__security_cookie
0x180025198  xor     rax, rsp
0x18002519b  mov     [rbp+57h+var_10], rax
0x18002519f  mov     rbx, r9
0x1800251a2  mov     rdi, r8
0x1800251a5  mov     rsi, rdx
0x1800251a8  mov     r14, rcx
0x1800251ab  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x1800251b0  mov     r10, rax
0x1800251b3  cmp     dword ptr [rax], 5
0x1800251b6  jbe     loc_180025308
0x1800251bc  movups  xmm0, xmmword ptr [rsi]
0x1800251bf  mov     r9, [rbx]
0x1800251c2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800251c9  mov     r8, [rdi]
0x1800251cc  mov     rdx, [r14]
0x1800251cf  movups  [rbp+57h+var_98], xmm0
0x1800251d3  test    r9, r9
0x1800251d6  jz      short loc_1800251F6
0x1800251d8  mov     rcx, rax
0x1800251db  nop     dword ptr [rax+rax+00h]
0x1800251e0  cmp     word ptr [r9+rcx*2+2], 0
0x1800251e7  lea     rcx, [rcx+1]
0x1800251eb  jnz     short loc_1800251E0
0x1800251ed  lea     ecx, ds:2[rcx*2]
0x1800251f4  jmp     short loc_180025202
0x1800251f6  lea     r9, Src
0x1800251fd  mov     ecx, 2
0x180025202  mov     [rbp+57h+var_20], r9
0x180025206  xor     r9d, r9d; RelatedActivityId
0x180025209  mov     [rbp+57h+var_18], ecx
0x18002520c  mov     [rbp+57h+var_14], r9d
0x180025210  test    r8, r8
0x180025213  jz      short loc_180025235
0x180025215  mov     rcx, rax
0x180025218  nop     dword ptr [rax+rax+00000000h]
0x180025220  cmp     [r8+rcx*2+2], r9w
0x180025226  lea     rcx, [rcx+1]
0x18002522a  jnz     short loc_180025220
0x18002522c  lea     ecx, ds:2[rcx*2]
0x180025233  jmp     short loc_180025241
0x180025235  lea     r8, Src
0x18002523c  mov     ecx, 2
0x180025241  mov     [rbp+57h+var_28], ecx
0x180025244  lea     rcx, [rbp+57h+var_98]
0x180025248  mov     [rbp+57h+var_40], rcx
0x18002524c  mov     [rbp+57h+var_30], r8
0x180025250  mov     [rbp+57h+var_24], r9d
0x180025254  mov     [rbp+57h+var_38], 10h
0x18002525c  test    rdx, rdx
0x18002525f  jz      short loc_180025276
0x180025261  cmp     [rdx+rax*2+2], r9w
0x180025267  lea     rax, [rax+1]
0x18002526b  jnz     short loc_180025261
0x18002526d  lea     eax, ds:2[rax*2]
0x180025274  jmp     short loc_180025282
0x180025276  lea     rdx, Src
0x18002527d  mov     eax, 2
0x180025282  mov     [rbp+57h+var_48], eax
0x180025285  lea     rcx, _TraceLoggingMetadata
0x18002528c  movzx   eax, cs:word_18004D408
0x180025293  xor     r8d, r8d; ActivityId
0x180025296  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180025299  mov     rax, [r10+8]
0x18002529d  mov     [rbp+57h+var_70.Ptr], rax
0x1800252a1  mov     [rbp+57h+var_50], rdx
0x1800252a5  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800252a9  mov     [rbp+57h+var_44], r9d
0x1800252ad  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800252b4  mov     [rbp+57h+EventDescriptor.Keyword], r9
0x1800252b8  movzx   eax, word ptr [rax]
0x1800252bb  mov     [rbp+57h+var_70.Size], eax
0x1800252be  lea     rax, word_18004D412
0x1800252c5  mov     [rbp+57h+var_60], rax
0x1800252c9  lea     rax, _TraceLoggingMetadataEnd
0x1800252d0  sub     eax, ecx
0x1800252d2  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1800252d9  mov     [rbp+57h+var_58], 5Ch ; '\'
0x1800252e0  mov     [rbp+57h+var_54], 1
0x1800252e7  mov     [rbp+57h+var_A0], eax
0x1800252ea  mov     eax, [rbp+57h+var_A0]
0x1800252ed  mov     rcx, [r10+20h]; RegHandle
0x1800252f1  lea     rax, [rbp+57h+var_70]
0x1800252f5  mov     [rsp+0D0h+UserData], rax; UserData
0x1800252fa  mov     [rsp+0D0h+UserDataCount], 6; UserDataCount
0x180025302  call    cs:__imp_EventWriteTransfer
0x180025308  mov     rcx, [rbp+57h+var_10]
0x18002530c  xor     rcx, rsp; StackCookie
0x18002530f  call    __security_check_cookie
0x180025314  lea     r11, [rsp+0D0h+var_s0]
0x18002531c  mov     rbx, [r11+10h]
0x180025320  mov     rsi, [r11+18h]
0x180025324  mov     rdi, [r11+20h]
0x180025328  mov     r14, [r11+28h]
0x18002532c  mov     rsp, r11
0x18002532f  pop     rbp
0x180025330  retn
```
