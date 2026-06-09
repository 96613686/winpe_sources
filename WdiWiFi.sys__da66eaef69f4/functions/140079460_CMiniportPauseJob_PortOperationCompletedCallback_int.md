# CMiniportPauseJob::PortOperationCompletedCallback(int)

- ea: `0x140079460`
- end: `0x140079613`
- name: `?PortOperationCompletedCallback@CMiniportPauseJob@@MEAAXH@Z`
- size: `435`
- prototype: `void __fastcall(CMiniportPauseJob *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x140079460`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisMPauseComplete` at `0x1400795be`
- `NDIS!NdisMPauseComplete` at `0x1400795be`

## pseudocode

```c
void __fastcall CMiniportPauseJob::PortOperationCompletedCallback(CMiniportPauseJob *this, int a2)
{
  int v2; // ebx
  MINIPORT_WDI_POST_PAUSE_HANDLER PostPauseHandler; // rsi
  int v5; // eax
  int v6; // r9d
  CAdapter *m_pAdapter; // rcx
  int v8; // edx
  __int64 v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+28h] [rbp-40h]

  v2 = a2;
  PostPauseHandler = this->m_pAdapter->m_MiniportDriver->m_MiniportWdiCharacteristics.PostPauseHandler;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      194,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
  }
  if ( !PostPauseHandler )
    goto LABEL_17;
  if ( v2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v6 = 197;
    v10 = v2;
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
        195,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
    }
    v5 = ((__int64 (__fastcall *)(void *, _NDIS_MINIPORT_PAUSE_PARAMETERS *))PostPauseHandler)(
           this->m_pAdapter->m_MiniportAdapterContext,
           this->m_PauseParameters);
    v2 = v5;
    if ( !v5 )
      goto LABEL_17;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v6 = 196;
    v10 = v5;
  }
  LOBYTE(a2) = 2;
  WPP_RECORDER_SF_D(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    1,
    v6,
    (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
    v10);
LABEL_17:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v9) = v2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      198,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      v9);
  }
LABEL_21:
  m_pAdapter = this->m_pAdapter;
  this->m_PauseParameters = 0;
  NdisMPauseComplete(m_pAdapter->m_MiniportAdapterHandle);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v9) = v2;
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      199,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      v9);
  }
}

```

## disassembly

```asm
0x140079460  push    rbx
0x140079462  push    rbp
0x140079463  push    rsi
0x140079464  push    rdi
0x140079465  push    r12
0x140079467  push    r13
0x140079469  push    r15
0x14007946b  sub     rsp, 30h
0x14007946f  mov     rax, [rcx+200h]
0x140079476  mov     ebx, edx
0x140079478  mov     rdi, rcx
0x14007947b  mov     r8, [rax+68h]
0x14007947f  mov     rsi, [r8+108h]
0x140079486  xor     ebp, ebp; __annotation("TMF:",
0x140079488  lea     r15, WPP_RECORDER_INITIALIZED
0x14007948f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140079496  lea     r13, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x14007949d  lea     r12d, [rbp+1]
0x1400794a1  jz      short loc_1400794CF
0x1400794a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794aa  cmp     byte ptr [rcx+29h], 5
0x1400794ae  jnb     short loc_1400794B6
0x1400794b0  cmp     [rcx+48h], bp
0x1400794b4  jz      short loc_1400794CF
0x1400794b6  mov     rcx, [rcx+40h]
0x1400794ba  mov     r9d, 0C2h
0x1400794c0  mov     r8d, r12d
0x1400794c3  mov     [rsp+68h+var_48], r13
0x1400794c8  mov     dl, 5
0x1400794ca  call    WPP_RECORDER_SF_
0x1400794cf  test    rsi, rsi
0x1400794d2  jz      loc_140079573
0x1400794d8  test    ebx, ebx
0x1400794da  jnz     short loc_140079546
0x1400794dc  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400794e3  jz      short loc_140079511
0x1400794e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794ec  cmp     byte ptr [rcx+29h], 5
0x1400794f0  jnb     short loc_1400794F8
0x1400794f2  cmp     [rcx+48h], bp
0x1400794f6  jz      short loc_140079511
0x1400794f8  mov     rcx, [rcx+40h]
0x1400794fc  mov     r9d, 0C3h
0x140079502  mov     r8d, r12d
0x140079505  mov     [rsp+68h+var_48], r13
0x14007950a  mov     dl, 5
0x14007950c  call    WPP_RECORDER_SF_
0x140079511  mov     rcx, [rdi+200h]
0x140079518  mov     rax, rsi
0x14007951b  mov     rdx, [rdi+218h]
0x140079522  mov     rcx, [rcx+60h]
0x140079526  call    _guard_dispatch_icall
0x14007952b  mov     ebx, eax
0x14007952d  test    eax, eax
0x14007952f  jz      short loc_140079573
0x140079531  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140079538  jz      short loc_1400795AC
0x14007953a  mov     r9d, 0C4h
0x140079540  mov     dword ptr [rsp+68h+var_40], eax
0x140079544  jmp     short loc_140079559
0x140079546  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14007954d  jz      short loc_1400795AC
0x14007954f  mov     r9d, 0C5h
0x140079555  mov     dword ptr [rsp+68h+var_40], ebx
0x140079559  mov     rcx, cs:WPP_GLOBAL_Control
0x140079560  mov     r8d, r12d
0x140079563  mov     dl, 2
0x140079565  mov     [rsp+68h+var_48], r13
0x14007956a  mov     rcx, [rcx+40h]
0x14007956e  call    WPP_RECORDER_SF_D
0x140079573  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14007957a  jz      short loc_1400795AC
0x14007957c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079583  cmp     byte ptr [rcx+29h], 5
0x140079587  jnb     short loc_14007958F
0x140079589  cmp     [rcx+48h], bp
0x14007958d  jz      short loc_1400795AC
0x14007958f  mov     rcx, [rcx+40h]
0x140079593  mov     r9d, 0C6h
0x140079599  mov     dword ptr [rsp+68h+var_40], ebx
0x14007959d  mov     r8d, r12d
0x1400795a0  mov     dl, 5
0x1400795a2  mov     [rsp+68h+var_48], r13
0x1400795a7  call    WPP_RECORDER_SF_D
0x1400795ac  mov     rcx, [rdi+200h]
0x1400795b3  mov     [rdi+218h], rbp
0x1400795ba  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x1400795be  call    cs:__imp_NdisMPauseComplete
0x1400795c5  nop     dword ptr [rax+rax+00h]
0x1400795ca  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400795d1  jz      short loc_140079603
0x1400795d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400795da  cmp     byte ptr [rcx+29h], 5
0x1400795de  jnb     short loc_1400795E6
0x1400795e0  cmp     [rcx+48h], bp
0x1400795e4  jz      short loc_140079603
0x1400795e6  mov     rcx, [rcx+40h]
0x1400795ea  mov     r9d, 0C7h
0x1400795f0  mov     dword ptr [rsp+68h+var_40], ebx
0x1400795f4  mov     r8d, r12d
0x1400795f7  mov     dl, 5
0x1400795f9  mov     [rsp+68h+var_48], r13
0x1400795fe  call    WPP_RECORDER_SF_D
0x140079603  add     rsp, 30h
0x140079607  pop     r15
0x140079609  pop     r13
0x14007960b  pop     r12
0x14007960d  pop     rdi
0x14007960e  pop     rsi
0x14007960f  pop     rbp
0x140079610  pop     rbx
0x140079611  retn
```
