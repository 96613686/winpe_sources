# CNdisHook::Cleanup(void)

- ea: `0x1400d52cc`
- end: `0x1400d53a2`
- name: `?Cleanup@CNdisHook@@QEAAXXZ`
- size: `214`
- prototype: `void __fastcall(CNdisHook *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14009fa4c`
- `0x1400d5160`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x1400d52cc`

## import_xrefs

- `NETIO!NmrDeregisterProvider` at `0x1400d5331`
- `NETIO!NmrDeregisterProvider` at `0x1400d5331`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1400d534a`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1400d534a`

## pseudocode

```c
void __fastcall CNdisHook::Cleanup(CNdisHook *this)
{
  NTSTATUS v2; // edi
  void *m_NmrProviderHandle; // rcx
  NTSTATUS v4; // [rsp+28h] [rbp-30h]

  v2 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      14,
      (__int64)WPP_ff5e4e9f36423a4802a02e039b18e1f3_Traceguids);
  }
  if ( this->m_NdisSupportsHook )
  {
    m_NmrProviderHandle = this->m_NmrProviderHandle;
    if ( m_NmrProviderHandle )
    {
      v2 = NmrDeregisterProvider(m_NmrProviderHandle);
      if ( v2 == 259 )
        v2 = NmrWaitForProviderDeregisterComplete(this->m_NmrProviderHandle);
      this->m_NmrProviderHandle = 0;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v4 = v2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      15,
      (__int64)WPP_ff5e4e9f36423a4802a02e039b18e1f3_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x1400d52cc  push    rbx
0x1400d52ce  push    rbp
0x1400d52cf  push    rsi
0x1400d52d0  push    rdi
0x1400d52d1  push    r15
0x1400d52d3  sub     rsp, 30h
0x1400d52d7  xor     esi, esi
0x1400d52d9  mov     rbx, rcx
0x1400d52dc  mov     edi, esi
0x1400d52de  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d52e5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400d52ec  lea     r15, WPP_ff5e4e9f36423a4802a02e039b18e1f3_Traceguids
0x1400d52f3  jz      short loc_1400D5322
0x1400d52f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d52fc  cmp     byte ptr [rcx+29h], 5
0x1400d5300  jnb     short loc_1400D5308
0x1400d5302  cmp     [rcx+48h], si
0x1400d5306  jz      short loc_1400D5322
0x1400d5308  mov     rcx, [rcx+40h]
0x1400d530c  mov     r9d, 0Eh
0x1400d5312  mov     dl, 5
0x1400d5314  mov     [rsp+58h+var_38], r15
0x1400d5319  lea     r8d, [r9-0Dh]
0x1400d531d  call    WPP_RECORDER_SF_
0x1400d5322  cmp     [rbx+20h], sil
0x1400d5326  jz      short loc_1400D535C
0x1400d5328  mov     rcx, [rbx+8]; NmrProviderHandle
0x1400d532c  test    rcx, rcx
0x1400d532f  jz      short loc_1400D535C
0x1400d5331  call    cs:__imp_NmrDeregisterProvider
0x1400d5338  nop     dword ptr [rax+rax+00h]
0x1400d533d  mov     edi, eax
0x1400d533f  cmp     eax, 103h
0x1400d5344  jnz     short loc_1400D5358
0x1400d5346  mov     rcx, [rbx+8]; NmrProviderHandle
0x1400d534a  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x1400d5351  nop     dword ptr [rax+rax+00h]
0x1400d5356  mov     edi, eax
0x1400d5358  mov     [rbx+8], rsi
0x1400d535c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400d5363  jz      short loc_1400D5396
0x1400d5365  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d536c  cmp     byte ptr [rcx+29h], 5
0x1400d5370  jnb     short loc_1400D5378
0x1400d5372  cmp     [rcx+48h], si
0x1400d5376  jz      short loc_1400D5396
0x1400d5378  mov     rcx, [rcx+40h]
0x1400d537c  mov     r9d, 0Fh
0x1400d5382  mov     [rsp+58h+var_30], edi
0x1400d5386  mov     dl, 5
0x1400d5388  mov     [rsp+58h+var_38], r15
0x1400d538d  lea     r8d, [r9-0Eh]
0x1400d5391  call    WPP_RECORDER_SF_D
0x1400d5396  add     rsp, 30h
0x1400d539a  pop     r15
0x1400d539c  pop     rdi
0x1400d539d  pop     rsi
0x1400d539e  pop     rbp
0x1400d539f  pop     rbx
0x1400d53a0  retn
```
