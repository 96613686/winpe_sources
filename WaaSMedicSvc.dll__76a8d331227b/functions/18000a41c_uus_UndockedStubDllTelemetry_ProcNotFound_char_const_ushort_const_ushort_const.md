# uus::UndockedStubDllTelemetry::ProcNotFound(char const *,ushort const *,ushort const *)

- ea: `0x18000a41c`
- end: `0x18000a567`
- name: `?ProcNotFound@UndockedStubDllTelemetry@uus@@SAXPEBDPEBG1@Z`
- size: `331`
- prototype: `void __fastcall(const char *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b900`
- `0x18000b9d0`
- `0x18000bac0`

## callees

- `0x18000163c`
- `0x180002200`
- `0x18000a41c`
- `0x18000a570`

## pseudocode

```c
void __fastcall uus::UndockedStubDllTelemetry::ProcNotFound(
        const char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r10
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rdx
  int v11; // edx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v16; // [rsp+60h] [rbp-19h]
  __int64 v17; // [rsp+68h] [rbp-11h]
  const char *v18; // [rsp+70h] [rbp-9h]
  int v19; // [rsp+78h] [rbp-1h]
  int v20; // [rsp+7Ch] [rbp+3h]
  const unsigned __int16 *v21; // [rsp+80h] [rbp+7h]
  int v22; // [rsp+88h] [rbp+Fh]
  int v23; // [rsp+8Ch] [rbp+13h]
  const unsigned __int16 *v24; // [rsp+90h] [rbp+17h]
  int v25; // [rsp+98h] [rbp+1Fh]
  int v26; // [rsp+9Ch] [rbp+23h]

  v6 = uus::UndockedStubDllTelemetry::Provider();
  v7 = v6;
  if ( *(_DWORD *)v6 > 5u
    && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
  {
    v8 = -1;
    v14 = 0x1000000;
    v9 = 2;
    if ( a3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a3[v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      a3 = (const unsigned __int16 *)&dword_18000F0AC;
      v11 = 2;
    }
    v24 = a3;
    v25 = v11;
    v26 = 0;
    if ( a2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v9 = 2 * v12 + 2;
    }
    else
    {
      a2 = (const unsigned __int16 *)&dword_18000F0AC;
    }
    v21 = a2;
    v22 = v9;
    v23 = 0;
    if ( a1 )
    {
      do
        ++v8;
      while ( a1[v8] );
      v13 = v8 + 1;
    }
    else
    {
      a1 = (const char *)&byte_18000EB27;
      v13 = 1;
    }
    v19 = v13;
    v18 = a1;
    v16 = &v14;
    v20 = 0;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(v7, byte_18000F589, 0, 0, 6, v15, v14);
  }
}

```

## disassembly

```asm
0x18000a41c  push    rbp
0x18000a41e  push    rbx
0x18000a41f  push    rsi
0x18000a420  push    rdi
0x18000a421  lea     rbp, [rsp-3Fh]
0x18000a426  sub     rsp, 0B8h
0x18000a42d  mov     rax, cs:__security_cookie
0x18000a434  xor     rax, rsp
0x18000a437  mov     [rbp+57h+var_30], rax
0x18000a43b  mov     rbx, r8
0x18000a43e  mov     rdi, rdx
0x18000a441  mov     rsi, rcx
0x18000a444  call    ?Provider@UndockedStubDllTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedStubDllTelemetry::Provider(void)
0x18000a449  mov     r10, rax
0x18000a44c  mov     r9d, [rax]
0x18000a44f  cmp     r9d, 5
0x18000a453  jbe     loc_18000A54F
0x18000a459  mov     rdx, [rax+18h]
0x18000a45d  mov     r9, [rax+10h]
0x18000a461  mov     rax, 400000000000h
0x18000a46b  test    rax, r9
0x18000a46e  jz      loc_18000A54F
0x18000a474  mov     rcx, rdx
0x18000a477  and     rcx, rax
0x18000a47a  cmp     rcx, rdx
0x18000a47d  jnz     loc_18000A54F
0x18000a483  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a487  mov     [rbp+57h+var_A0], 1000000h
0x18000a48f  xor     r8d, r8d
0x18000a492  mov     ecx, 2
0x18000a497  test    rbx, rbx
0x18000a49a  jz      short loc_18000A4B2
0x18000a49c  mov     rdx, rax
0x18000a49f  inc     rdx
0x18000a4a2  cmp     [rbx+rdx*2], r8w
0x18000a4a7  jnz     short loc_18000A49F
0x18000a4a9  lea     edx, ds:2[rdx*2]
0x18000a4b0  jmp     short loc_18000A4BB
0x18000a4b2  lea     rbx, dword_18000F0AC
0x18000a4b9  mov     edx, ecx
0x18000a4bb  mov     [rbp+57h+var_40], rbx
0x18000a4bf  mov     [rbp+57h+var_38], edx
0x18000a4c2  mov     [rbp+57h+var_34], r8d
0x18000a4c6  test    rdi, rdi
0x18000a4c9  jz      short loc_18000A4E1
0x18000a4cb  mov     rcx, rax
0x18000a4ce  inc     rcx
0x18000a4d1  cmp     [rdi+rcx*2], r8w
0x18000a4d6  jnz     short loc_18000A4CE
0x18000a4d8  lea     ecx, ds:2[rcx*2]
0x18000a4df  jmp     short loc_18000A4E8
0x18000a4e1  lea     rdi, dword_18000F0AC
0x18000a4e8  mov     [rbp+57h+var_50], rdi
0x18000a4ec  mov     [rbp+57h+var_48], ecx
0x18000a4ef  mov     [rbp+57h+var_44], r8d
0x18000a4f3  test    rsi, rsi
0x18000a4f6  jz      short loc_18000A505
0x18000a4f8  inc     rax
0x18000a4fb  cmp     [rsi+rax], r8b
0x18000a4ff  jnz     short loc_18000A4F8
0x18000a501  inc     eax
0x18000a503  jmp     short loc_18000A511
0x18000a505  lea     rsi, byte_18000EB27
0x18000a50c  mov     eax, 1
0x18000a511  mov     [rbp+57h+var_58], eax
0x18000a514  lea     rdx, byte_18000F589
0x18000a51b  lea     rax, [rbp+57h+var_A0]
0x18000a51f  mov     [rbp+57h+var_60], rsi
0x18000a523  mov     [rbp+57h+var_70], rax
0x18000a527  xor     r9d, r9d
0x18000a52a  lea     rax, [rbp+57h+var_90]
0x18000a52e  mov     [rbp+57h+var_54], r8d
0x18000a532  mov     [rsp+0D0h+var_A8], rax
0x18000a537  mov     rcx, r10
0x18000a53a  mov     [rsp+0D0h+var_B0], 6
0x18000a542  mov     [rbp+57h+var_68], 8
0x18000a54a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a54f  mov     rcx, [rbp+57h+var_30]
0x18000a553  xor     rcx, rsp; StackCookie
0x18000a556  call    __security_check_cookie
0x18000a55b  add     rsp, 0B8h
0x18000a562  pop     rdi
0x18000a563  pop     rsi
0x18000a564  pop     rbx
0x18000a565  pop     rbp
0x18000a566  retn
```
