# CMiniportRestartJob::PortOperationCompletedCallback(int)

- ea: `0x140079c80`
- end: `0x140079e35`
- name: `?PortOperationCompletedCallback@CMiniportRestartJob@@MEAAXH@Z`
- size: `437`
- prototype: `void __fastcall(CMiniportRestartJob *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x140079c80`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisMRestartComplete` at `0x140079dde`
- `NDIS!NdisMRestartComplete` at `0x140079dde`

## pseudocode

```c
void __fastcall CMiniportRestartJob::PortOperationCompletedCallback(CMiniportRestartJob *this, NDIS_STATUS a2)
{
  NDIS_STATUS v2; // ebx
  MINIPORT_WDI_POST_RESTART_HANDLER PostRestartHandler; // rdi
  NDIS_STATUS v5; // eax
  int v6; // r9d
  int v7; // edx
  __int64 v8; // [rsp+28h] [rbp-40h]
  NDIS_STATUS v9; // [rsp+28h] [rbp-40h]

  v2 = a2;
  PostRestartHandler = this->m_pAdapter->m_MiniportDriver->m_MiniportWdiCharacteristics.PostRestartHandler;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      200,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
  }
  if ( !PostRestartHandler )
    goto LABEL_17;
  if ( v2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v6 = 203;
    v9 = v2;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        201,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
    }
    v5 = ((__int64 (__fastcall *)(void *, _NDIS_MINIPORT_RESTART_PARAMETERS *))PostRestartHandler)(
           this->m_pAdapter->m_MiniportAdapterContext,
           this->m_RestartParameters);
    v2 = v5;
    if ( !v5 )
      goto LABEL_17;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v6 = 202;
    v9 = v5;
  }
  LOBYTE(a2) = 2;
  WPP_RECORDER_SF_D(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    1,
    v6,
    (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
    v9);
LABEL_17:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v8) = v2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      204,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      v8);
  }
LABEL_21:
  NdisMRestartComplete(this->m_pAdapter->m_MiniportAdapterHandle, v2);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v8) = v2;
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      205,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      v8);
  }
}

```

## disassembly

```asm
0x140079c80  push    rbx
0x140079c82  push    rsi
0x140079c83  push    rdi
0x140079c84  push    r12
0x140079c86  push    r13
0x140079c88  push    r14
0x140079c8a  push    r15
0x140079c8c  sub     rsp, 30h
0x140079c90  mov     rax, [rcx+200h]
0x140079c97  mov     ebx, edx
0x140079c99  mov     rsi, rcx
0x140079c9c  mov     r8, [rax+68h]
0x140079ca0  mov     rdi, [r8+110h]
0x140079ca7  xor     r14d, r14d; __annotation("TMF:",
0x140079caa  lea     r15, WPP_RECORDER_INITIALIZED
0x140079cb1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140079cb8  lea     r13, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140079cbf  lea     r12d, [r14+1]
0x140079cc3  jz      short loc_140079CF2
0x140079cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ccc  cmp     byte ptr [rcx+29h], 5
0x140079cd0  jnb     short loc_140079CD9
0x140079cd2  cmp     [rcx+48h], r14w
0x140079cd7  jz      short loc_140079CF2
0x140079cd9  mov     rcx, [rcx+40h]
0x140079cdd  mov     r9d, 0C8h
0x140079ce3  mov     r8d, r12d
0x140079ce6  mov     [rsp+68h+var_48], r13
0x140079ceb  mov     dl, 5
0x140079ced  call    WPP_RECORDER_SF_
0x140079cf2  test    rdi, rdi
0x140079cf5  jz      loc_140079D97
0x140079cfb  test    ebx, ebx
0x140079cfd  jnz     short loc_140079D6A
0x140079cff  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079d06  jz      short loc_140079D35
0x140079d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d0f  cmp     byte ptr [rcx+29h], 5
0x140079d13  jnb     short loc_140079D1C
0x140079d15  cmp     [rcx+48h], r14w
0x140079d1a  jz      short loc_140079D35
0x140079d1c  mov     rcx, [rcx+40h]
0x140079d20  mov     r9d, 0C9h
0x140079d26  mov     r8d, r12d
0x140079d29  mov     [rsp+68h+var_48], r13
0x140079d2e  mov     dl, 5
0x140079d30  call    WPP_RECORDER_SF_
0x140079d35  mov     rcx, [rsi+200h]
0x140079d3c  mov     rax, rdi
0x140079d3f  mov     rdx, [rsi+218h]
0x140079d46  mov     rcx, [rcx+60h]
0x140079d4a  call    _guard_dispatch_icall
0x140079d4f  mov     ebx, eax
0x140079d51  test    eax, eax
0x140079d53  jz      short loc_140079D97
0x140079d55  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079d5c  jz      short loc_140079DD1
0x140079d5e  mov     r9d, 0CAh
0x140079d64  mov     dword ptr [rsp+68h+var_40], eax
0x140079d68  jmp     short loc_140079D7D
0x140079d6a  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079d71  jz      short loc_140079DD1
0x140079d73  mov     r9d, 0CBh
0x140079d79  mov     dword ptr [rsp+68h+var_40], ebx
0x140079d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d84  mov     r8d, r12d
0x140079d87  mov     dl, 2
0x140079d89  mov     [rsp+68h+var_48], r13
0x140079d8e  mov     rcx, [rcx+40h]
0x140079d92  call    WPP_RECORDER_SF_D
0x140079d97  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079d9e  jz      short loc_140079DD1
0x140079da0  mov     rcx, cs:WPP_GLOBAL_Control
0x140079da7  cmp     byte ptr [rcx+29h], 5
0x140079dab  jnb     short loc_140079DB4
0x140079dad  cmp     [rcx+48h], r14w
0x140079db2  jz      short loc_140079DD1
0x140079db4  mov     rcx, [rcx+40h]
0x140079db8  mov     r9d, 0CCh
0x140079dbe  mov     dword ptr [rsp+68h+var_40], ebx
0x140079dc2  mov     r8d, r12d
0x140079dc5  mov     dl, 5
0x140079dc7  mov     [rsp+68h+var_48], r13
0x140079dcc  call    WPP_RECORDER_SF_D
0x140079dd1  mov     rcx, [rsi+200h]
0x140079dd8  mov     edx, ebx; Status
0x140079dda  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140079dde  call    cs:__imp_NdisMRestartComplete
0x140079de5  nop     dword ptr [rax+rax+00h]
0x140079dea  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079df1  jz      short loc_140079E24
0x140079df3  mov     rcx, cs:WPP_GLOBAL_Control
0x140079dfa  cmp     byte ptr [rcx+29h], 5
0x140079dfe  jnb     short loc_140079E07
0x140079e00  cmp     [rcx+48h], r14w
0x140079e05  jz      short loc_140079E24
0x140079e07  mov     rcx, [rcx+40h]
0x140079e0b  mov     r9d, 0CDh
0x140079e11  mov     dword ptr [rsp+68h+var_40], ebx
0x140079e15  mov     r8d, r12d
0x140079e18  mov     dl, 5
0x140079e1a  mov     [rsp+68h+var_48], r13
0x140079e1f  call    WPP_RECORDER_SF_D
0x140079e24  add     rsp, 30h
0x140079e28  pop     r15
0x140079e2a  pop     r14
0x140079e2c  pop     r13
0x140079e2e  pop     r12
0x140079e30  pop     rdi
0x140079e31  pop     rsi
0x140079e32  pop     rbx
0x140079e33  retn
```
