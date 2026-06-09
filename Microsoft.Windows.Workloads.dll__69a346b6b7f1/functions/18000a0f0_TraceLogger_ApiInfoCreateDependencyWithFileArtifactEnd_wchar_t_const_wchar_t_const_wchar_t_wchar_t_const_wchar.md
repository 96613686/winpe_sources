# TraceLogger::ApiInfoCreateDependencyWithFileArtifactEnd<wchar_t const *,wchar_t const *,wchar_t * &>(wchar_t const * &&,wchar_t const * &&,wchar_t * &)

- ea: `0x18000a0f0`
- end: `0x18000a2ad`
- name: `??$ApiInfoCreateDependencyWithFileArtifactEnd@PEB_WPEB_WAEAPEA_W@TraceLogger@@SAX$$QEAPEB_W0AEAPEA_W@Z`
- size: `445`
- prototype: `int __fastcall(const wchar_t **, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008a50`

## callees

- `0x18000a0f0`
- `0x1800119b0`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000a282`
- `ADVAPI32!EventWriteTransfer` at `0x18000a282`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TraceLogger::ApiInfoCreateDependencyWithFileArtifactEnd<wchar_t const *,wchar_t const *,wchar_t * &>(
        const wchar_t **a1,
        const wchar_t **a2,
        const wchar_t **a3)
{
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r10
  const wchar_t *v8; // r8
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  const wchar_t *v11; // r9
  __int64 v12; // rax
  bool v13; // zf
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  int *v21; // [rsp+60h] [rbp-58h]
  int v22; // [rsp+68h] [rbp-50h]
  int v23; // [rsp+6Ch] [rbp-4Ch]
  const wchar_t *v24; // [rsp+70h] [rbp-48h]
  int v25; // [rsp+78h] [rbp-40h]
  int v26; // [rsp+7Ch] [rbp-3Ch]
  const wchar_t *v27; // [rsp+80h] [rbp-38h]
  int v28; // [rsp+88h] [rbp-30h]
  int v29; // [rsp+8Ch] [rbp-2Ch]
  const wchar_t *v30; // [rsp+90h] [rbp-28h]
  int v31; // [rsp+98h] [rbp-20h]
  int v32; // [rsp+9Ch] [rbp-1Ch]

  v6 = TraceLogger::Provider();
  v7 = v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    v8 = *a3;
    v9 = -1;
    v10 = *a2;
    v11 = *a1;
    if ( *a3 )
    {
      v12 = -1;
      do
        v13 = v8[++v12] == 0;
      while ( !v13 );
      v14 = 2 * v12 + 2;
    }
    else
    {
      v8 = &Src;
      v14 = 2;
    }
    v30 = v8;
    v31 = v14;
    v32 = 0;
    if ( v10 )
    {
      v15 = -1;
      do
        v13 = v10[++v15] == 0;
      while ( !v13 );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v10 = &Src;
      v16 = 2;
    }
    v27 = v10;
    v28 = v16;
    v29 = 0;
    if ( v11 )
    {
      do
        v13 = v11[++v9] == 0;
      while ( !v13 );
      v17 = 2 * v9 + 2;
    }
    else
    {
      v11 = &Src;
      v17 = 2;
    }
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *((_QWORD *)v7 + 1);
    v25 = v17;
    v24 = v11;
    v26 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v21 = &dword_18004D04C;
    UserData.Reserved = 2;
    v22 = 100;
    v23 = 1;
    LODWORD(v6) = EventWriteTransfer(*((_QWORD *)v7 + 4), &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return (int)v6;
}

```

## disassembly

```asm
0x18000a0f0  mov     [rsp+arg_0], rbx
0x18000a0f5  mov     [rsp+arg_8], rsi
0x18000a0fa  push    rdi
0x18000a0fb  sub     rsp, 0B0h
0x18000a102  mov     rax, cs:__security_cookie
0x18000a109  xor     rax, rsp
0x18000a10c  mov     [rsp+0B8h+var_18], rax
0x18000a114  mov     rbx, r8
0x18000a117  mov     rdi, rdx
0x18000a11a  mov     rsi, rcx
0x18000a11d  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000a122  mov     r10, rax
0x18000a125  cmp     dword ptr [rax], 5
0x18000a128  jbe     loc_18000A288
0x18000a12e  mov     r8, [rbx]
0x18000a131  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a138  mov     rdx, [rdi]
0x18000a13b  mov     r9, [rsi]
0x18000a13e  test    r8, r8
0x18000a141  jz      short loc_18000A166
0x18000a143  mov     rax, rcx
0x18000a146  nop     word ptr [rax+rax+00000000h]
0x18000a150  cmp     word ptr [r8+rax*2+2], 0
0x18000a157  lea     rax, [rax+1]
0x18000a15b  jnz     short loc_18000A150
0x18000a15d  lea     eax, ds:2[rax*2]
0x18000a164  jmp     short loc_18000A172
0x18000a166  lea     r8, Src
0x18000a16d  mov     eax, 2
0x18000a172  mov     [rsp+0B8h+var_28], r8
0x18000a17a  xor     r8d, r8d; ActivityId
0x18000a17d  mov     [rsp+0B8h+var_20], eax
0x18000a184  mov     [rsp+0B8h+var_1C], r8d
0x18000a18c  test    rdx, rdx
0x18000a18f  jz      short loc_18000A1A9
0x18000a191  mov     rax, rcx
0x18000a194  cmp     [rdx+rax*2+2], r8w
0x18000a19a  lea     rax, [rax+1]
0x18000a19e  jnz     short loc_18000A194
0x18000a1a0  lea     eax, ds:2[rax*2]
0x18000a1a7  jmp     short loc_18000A1B5
0x18000a1a9  lea     rdx, Src
0x18000a1b0  mov     eax, 2
0x18000a1b5  mov     [rsp+0B8h+var_38], rdx
0x18000a1bd  mov     [rsp+0B8h+var_30], eax
0x18000a1c4  mov     [rsp+0B8h+var_2C], r8d
0x18000a1cc  test    r9, r9
0x18000a1cf  jz      short loc_18000A1E6
0x18000a1d1  cmp     [r9+rcx*2+2], r8w
0x18000a1d7  lea     rcx, [rcx+1]
0x18000a1db  jnz     short loc_18000A1D1
0x18000a1dd  lea     ecx, ds:2[rcx*2]
0x18000a1e4  jmp     short loc_18000A1F2
0x18000a1e6  lea     r9, Src
0x18000a1ed  mov     ecx, 2
0x18000a1f2  movzx   eax, cs:word_18004D042
0x18000a1f9  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x18000a1fe  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x18000a202  mov     rax, [r10+8]
0x18000a206  mov     [rsp+0B8h+var_68.Ptr], rax
0x18000a20b  mov     [rsp+0B8h+var_40], ecx
0x18000a20f  lea     rcx, _TraceLoggingMetadata
0x18000a216  mov     [rsp+0B8h+var_48], r9
0x18000a21b  xor     r9d, r9d; RelatedActivityId
0x18000a21e  mov     [rsp+0B8h+var_3C], r8d
0x18000a223  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x18000a22b  mov     [rsp+0B8h+EventDescriptor.Keyword], r8
0x18000a230  movzx   eax, word ptr [rax]
0x18000a233  mov     [rsp+0B8h+var_68.Size], eax
0x18000a237  lea     rax, dword_18004D04C
0x18000a23e  mov     [rsp+0B8h+var_58], rax
0x18000a243  lea     rax, _TraceLoggingMetadataEnd
0x18000a24a  sub     eax, ecx
0x18000a24c  mov     dword ptr [rsp+0B8h+var_68.0Ch], 2
0x18000a254  mov     [rsp+0B8h+var_50], 64h ; 'd'
0x18000a25c  mov     [rsp+0B8h+var_4C], 1
0x18000a264  mov     [rsp+0B8h+var_88], eax
0x18000a268  mov     eax, [rsp+0B8h+var_88]
0x18000a26c  mov     rcx, [r10+20h]; RegHandle
0x18000a270  lea     rax, [rsp+0B8h+var_68]
0x18000a275  mov     [rsp+0B8h+UserData], rax; UserData
0x18000a27a  mov     [rsp+0B8h+UserDataCount], 5; UserDataCount
0x18000a282  call    cs:__imp_EventWriteTransfer
0x18000a288  mov     rcx, [rsp+0B8h+var_18]
0x18000a290  xor     rcx, rsp; StackCookie
0x18000a293  call    __security_check_cookie
0x18000a298  lea     r11, [rsp+0B8h+var_8]
0x18000a2a0  mov     rbx, [r11+10h]
0x18000a2a4  mov     rsi, [r11+18h]
0x18000a2a8  mov     rsp, r11
0x18000a2ab  pop     rdi
0x18000a2ac  retn
```
