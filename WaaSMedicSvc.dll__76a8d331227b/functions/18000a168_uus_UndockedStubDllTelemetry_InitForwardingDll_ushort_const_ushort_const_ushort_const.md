# uus::UndockedStubDllTelemetry::InitForwardingDll(ushort const *,ushort const *,ushort const *)

- ea: `0x18000a168`
- end: `0x18000a2b1`
- name: `?InitForwardingDll@UndockedStubDllTelemetry@uus@@SAXPEBG00@Z`
- size: `329`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aa84`

## callees

- `0x18000163c`
- `0x180002200`
- `0x18000a168`
- `0x18000a570`

## pseudocode

```c
void __fastcall uus::UndockedStubDllTelemetry::InitForwardingDll(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r10
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rcx
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // ecx
  __int64 v14; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v16; // [rsp+60h] [rbp-19h]
  __int64 v17; // [rsp+68h] [rbp-11h]
  const unsigned __int16 *v18; // [rsp+70h] [rbp-9h]
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
    && (*((_QWORD *)v6 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x200000000000LL) == *((_QWORD *)v6 + 3) )
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
      v13 = 2 * v12 + 2;
    }
    else
    {
      a2 = (const unsigned __int16 *)&dword_18000F0AC;
      v13 = 2;
    }
    v21 = a2;
    v22 = v13;
    v23 = 0;
    if ( a1 )
    {
      do
        ++v8;
      while ( a1[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      a1 = (const unsigned __int16 *)&dword_18000F0AC;
    }
    v19 = v9;
    v16 = &v14;
    v18 = a1;
    v20 = 0;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(v7, &dword_18000F5E4, 0, 0, 6, v15, v14);
  }
}

```

## disassembly

```asm
0x18000a168  push    rbp
0x18000a16a  push    rbx
0x18000a16b  push    rsi
0x18000a16c  push    rdi
0x18000a16d  lea     rbp, [rsp-3Fh]
0x18000a172  sub     rsp, 0B8h
0x18000a179  mov     rax, cs:__security_cookie
0x18000a180  xor     rax, rsp
0x18000a183  mov     [rbp+57h+var_30], rax
0x18000a187  mov     rbx, r8
0x18000a18a  mov     rdi, rdx
0x18000a18d  mov     rsi, rcx
0x18000a190  call    ?Provider@UndockedStubDllTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedStubDllTelemetry::Provider(void)
0x18000a195  mov     r10, rax
0x18000a198  mov     r9d, [rax]
0x18000a19b  cmp     r9d, 5
0x18000a19f  jbe     loc_18000A299
0x18000a1a5  mov     r8, [rax+18h]
0x18000a1a9  mov     r9, [rax+10h]
0x18000a1ad  mov     rax, 200000000000h
0x18000a1b7  test    rax, r9
0x18000a1ba  jz      loc_18000A299
0x18000a1c0  mov     rcx, r8
0x18000a1c3  and     rcx, rax
0x18000a1c6  cmp     rcx, r8
0x18000a1c9  jnz     loc_18000A299
0x18000a1cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a1d3  mov     [rbp+57h+var_A0], 1000000h
0x18000a1db  xor     r8d, r8d
0x18000a1de  lea     r9, dword_18000F0AC
0x18000a1e5  mov     edx, 2
0x18000a1ea  test    rbx, rbx
0x18000a1ed  jz      short loc_18000A205
0x18000a1ef  mov     rcx, rax
0x18000a1f2  inc     rcx
0x18000a1f5  cmp     [rbx+rcx*2], r8w
0x18000a1fa  jnz     short loc_18000A1F2
0x18000a1fc  lea     ecx, ds:2[rcx*2]
0x18000a203  jmp     short loc_18000A20A
0x18000a205  mov     rbx, r9
0x18000a208  mov     ecx, edx
0x18000a20a  mov     [rbp+57h+var_40], rbx
0x18000a20e  mov     [rbp+57h+var_38], ecx
0x18000a211  mov     [rbp+57h+var_34], r8d
0x18000a215  test    rdi, rdi
0x18000a218  jz      short loc_18000A230
0x18000a21a  mov     rcx, rax
0x18000a21d  inc     rcx
0x18000a220  cmp     [rdi+rcx*2], r8w
0x18000a225  jnz     short loc_18000A21D
0x18000a227  lea     ecx, ds:2[rcx*2]
0x18000a22e  jmp     short loc_18000A235
0x18000a230  mov     rdi, r9
0x18000a233  mov     ecx, edx
0x18000a235  mov     [rbp+57h+var_50], rdi
0x18000a239  mov     [rbp+57h+var_48], ecx
0x18000a23c  mov     [rbp+57h+var_44], r8d
0x18000a240  test    rsi, rsi
0x18000a243  jz      short loc_18000A258
0x18000a245  inc     rax
0x18000a248  cmp     [rsi+rax*2], r8w
0x18000a24d  jnz     short loc_18000A245
0x18000a24f  lea     edx, ds:2[rax*2]
0x18000a256  jmp     short loc_18000A25B
0x18000a258  mov     rsi, r9
0x18000a25b  lea     rax, [rbp+57h+var_A0]
0x18000a25f  mov     [rbp+57h+var_58], edx
0x18000a262  mov     [rbp+57h+var_70], rax
0x18000a266  lea     rdx, dword_18000F5E4
0x18000a26d  lea     rax, [rbp+57h+var_90]
0x18000a271  mov     [rbp+57h+var_60], rsi
0x18000a275  mov     [rsp+0D0h+var_A8], rax
0x18000a27a  xor     r9d, r9d
0x18000a27d  mov     rcx, r10
0x18000a280  mov     [rsp+0D0h+var_B0], 6
0x18000a288  mov     [rbp+57h+var_54], r8d
0x18000a28c  mov     [rbp+57h+var_68], 8
0x18000a294  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a299  mov     rcx, [rbp+57h+var_30]
0x18000a29d  xor     rcx, rsp; StackCookie
0x18000a2a0  call    __security_check_cookie
0x18000a2a5  add     rsp, 0B8h
0x18000a2ac  pop     rdi
0x18000a2ad  pop     rsi
0x18000a2ae  pop     rbx
0x18000a2af  pop     rbp
0x18000a2b0  retn
```
