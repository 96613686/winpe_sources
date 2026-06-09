# Apx::ApfIpcIoLinkMgr::OnCmDeviceRemove(void)

- ea: `0x180026320`
- end: `0x180026451`
- name: `?OnCmDeviceRemove@ApfIpcIoLinkMgr@Apx@@AEAAXXZ`
- size: `305`
- prototype: `void __fastcall(unsigned __int64 this, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026ef0`

## callees

- `0x18000a12c`
- `0x180026320`
- `0x180027068`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002640e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002640e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026399`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800263eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800263eb`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800263dc`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800263dc`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::OnCmDeviceRemove(unsigned __int64 this, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  __int64 v5; // r8
  void *v6; // rcx
  __int64 v7; // r8
  void *v8; // rcx

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
      v4 = (char *)WPP_GLOBAL_Control;
    }
    if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 4u )
      WPP_SF_q(*((_QWORD *)v4 + 2), 59, a3, ~this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v6 = *(void **)(this + 88);
  *(_BYTE *)(this + 117) = 0;
  if ( v6 )
  {
    CancelIoEx(v6, 0);
    v8 = *(void **)(this + 88);
    if ( v8 )
    {
      CloseHandle(v8);
      *(_QWORD *)(this + 88) = 0;
    }
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(this + 56))(*(_QWORD *)(this + 64), 0, v7);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, v5, ~this);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180026320  mov     [rsp+arg_0], rbx
0x180026325  mov     [rsp+arg_8], rsi
0x18002632a  push    rdi
0x18002632b  sub     rsp, 20h
0x18002632f  mov     rbx, rcx
0x180026332  mov     rcx, cs:WPP_GLOBAL_Control
0x180026339  lea     rsi, WPP_GLOBAL_Control
0x180026340  cmp     rcx, rsi
0x180026343  jz      short loc_180026392
0x180026345  test    byte ptr [rcx+1Ch], 1
0x180026349  jz      short loc_18002636D
0x18002634b  cmp     byte ptr [rcx+19h], 5
0x18002634f  jb      short loc_18002636D
0x180026351  mov     rcx, [rcx+10h]
0x180026355  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x18002635c  mov     edx, 3Ah ; ':'
0x180026361  call    WPP_SF_
0x180026366  mov     rcx, cs:WPP_GLOBAL_Control
0x18002636d  cmp     rcx, rsi
0x180026370  jz      short loc_180026392
0x180026372  test    byte ptr [rcx+1Ch], 80h
0x180026376  jz      short loc_180026392
0x180026378  cmp     byte ptr [rcx+19h], 4
0x18002637c  jb      short loc_180026392
0x18002637e  mov     rcx, [rcx+10h]
0x180026382  mov     r9, rbx
0x180026385  not     r9
0x180026388  mov     edx, 3Bh ; ';'
0x18002638d  call    WPP_SF_q
0x180026392  lea     rdi, [rbx+10h]
0x180026396  mov     rcx, rdi; lpCriticalSection
0x180026399  call    cs:__imp_EnterCriticalSection
0x18002639f  mov     rcx, [rbx+58h]; hFile
0x1800263a3  mov     byte ptr [rbx+75h], 0
0x1800263a7  test    rcx, rcx
0x1800263aa  jnz     short loc_1800263DA
0x1800263ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263b3  cmp     rcx, rsi
0x1800263b6  jz      short loc_18002640B
0x1800263b8  test    byte ptr [rcx+1Ch], 80h
0x1800263bc  jz      short loc_18002640B
0x1800263be  cmp     byte ptr [rcx+19h], 4
0x1800263c2  jb      short loc_18002640B
0x1800263c4  mov     rcx, [rcx+10h]
0x1800263c8  not     rbx
0x1800263cb  mov     r9, rbx
0x1800263ce  mov     edx, 3Ch ; '<'
0x1800263d3  call    WPP_SF_q
0x1800263d8  jmp     short loc_18002640B
0x1800263da  xor     edx, edx; lpOverlapped
0x1800263dc  call    cs:__imp_CancelIoEx
0x1800263e2  mov     rcx, [rbx+58h]; hObject
0x1800263e6  test    rcx, rcx
0x1800263e9  jz      short loc_1800263F9
0x1800263eb  call    cs:__imp_CloseHandle
0x1800263f1  mov     qword ptr [rbx+58h], 0
0x1800263f9  mov     rcx, [rbx+40h]
0x1800263fd  mov     r8b, 1
0x180026400  mov     rax, [rbx+38h]
0x180026404  xor     edx, edx
0x180026406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002640b  mov     rcx, rdi; lpCriticalSection
0x18002640e  call    cs:__imp_LeaveCriticalSection
0x180026414  mov     rcx, cs:WPP_GLOBAL_Control
0x18002641b  cmp     rcx, rsi
0x18002641e  jz      short loc_180026441
0x180026420  test    byte ptr [rcx+1Ch], 1
0x180026424  jz      short loc_180026441
0x180026426  cmp     byte ptr [rcx+19h], 5
0x18002642a  jb      short loc_180026441
0x18002642c  mov     rcx, [rcx+10h]
0x180026430  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026437  mov     edx, 3Dh ; '='
0x18002643c  call    WPP_SF_
0x180026441  mov     rbx, [rsp+28h+arg_0]
0x180026446  mov     rsi, [rsp+28h+arg_8]
0x18002644b  add     rsp, 20h
0x18002644f  pop     rdi
0x180026450  retn
```
