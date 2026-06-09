# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)

- ea: `0x18002efa0`
- end: `0x18002f2a2`
- name: `?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `770`
- prototype: `__int64 __fastcall(__int64 **this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002a610`
- `0x18002b4d4`
- `0x18002c640`
- `0x18002e9e4`

## callees

- `0x18001140c`
- `0x18002aec0`
- `0x18002efa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f1b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f1b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1db`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002f10e`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002f10e`
- `deviceassociation!DafCloseAssociationContext` at `0x18002f1d3`
- `deviceassociation!DafCloseAssociationContext` at `0x18002f1d3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(__int64 **this)
{
  char v2; // si
  bool v3; // dl
  _BYTE *v4; // rcx
  bool v5; // dl
  bool v6; // dl
  __int64 v7; // rbx
  bool v8; // dl
  bool v9; // dl
  __int64 *v10; // rcx
  __int64 *v11; // rbp
  DWORD LastError; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  _BYTE *v15; // rcx
  bool v16; // dl
  _UNKNOWN **v17; // rax

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  _InterlockedExchange((volatile __int32 *)this + 35, 1);
  v4 = WPP_GLOBAL_Control;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v4 = WPP_GLOBAL_Control;
  }
  if ( *this && (unsigned __int64)(**this - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *((_DWORD *)this + 34) == 997 )
    {
      v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v7 = -1;
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_si(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      if ( *this )
        v7 = **this;
      CancelIoEx((HANDLE)v7, (LPOVERLAPPED)(this + 11));
    }
    v4 = WPP_GLOBAL_Control;
  }
  v8 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v4 + 2),
      v8,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
    v4 = WPP_GLOBAL_Control;
  }
  v9 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v4 + 2),
      v9,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
  v10 = this[257];
  if ( v10 )
    SetEvent(v10);
  v11 = this[255];
  if ( v11 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v11, v13, v14);
    SetLastError(LastError);
  }
  this[255] = 0;
  v15 = WPP_GLOBAL_Control;
  v16 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v17 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v15 = WPP_GLOBAL_Control;
    v17 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v15 == (_BYTE *)&WPP_GLOBAL_Control || v15[25] < 5u )
    v2 = 0;
  if ( v2 || v17 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v15 + 2), v2, v17 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v15 + 5));
  return 0;
}

```

## disassembly

```asm
0x18002efa0  push    rbx
0x18002efa2  push    rbp
0x18002efa3  push    rsi
0x18002efa4  push    rdi
0x18002efa5  push    r12
0x18002efa7  push    r13
0x18002efa9  push    r14
0x18002efab  sub     rsp, 60h
0x18002efaf  mov     rdi, rcx
0x18002efb2  lea     r14, WPP_GLOBAL_Control
0x18002efb9  mov     esi, 1
0x18002efbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efc5  cmp     rcx, r14
0x18002efc8  jz      short loc_18002EFD5
0x18002efca  cmp     byte ptr [rcx+19h], 5
0x18002efce  jb      short loc_18002EFD5
0x18002efd0  mov     dl, sil
0x18002efd3  jmp     short loc_18002EFD7
0x18002efd5  xor     dl, dl
0x18002efd7  lea     r12, WPP_RECORDER_INITIALIZED
0x18002efde  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002efe5  setnz   r8b
0x18002efe9  lea     r13, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002eff0  test    dl, dl
0x18002eff2  jnz     short loc_18002EFF9
0x18002eff4  test    r8b, r8b
0x18002eff7  jz      short loc_18002F017
0x18002eff9  mov     [rsp+98h+var_50], rdi
0x18002effe  mov     [rsp+98h+var_60], r13
0x18002f003  mov     [rsp+98h+var_68], 22h ; '"'
0x18002f00a  mov     r9, [rcx+28h]
0x18002f00e  mov     rcx, [rcx+10h]
0x18002f012  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f017  mov     eax, esi
0x18002f019  xchg    eax, [rdi+8Ch]
0x18002f01f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f026  cmp     rcx, r14
0x18002f029  jz      short loc_18002F036
0x18002f02b  cmp     byte ptr [rcx+19h], 5
0x18002f02f  jb      short loc_18002F036
0x18002f031  mov     dl, sil
0x18002f034  jmp     short loc_18002F038
0x18002f036  xor     dl, dl
0x18002f038  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002f03f  setnz   r8b
0x18002f043  test    dl, dl
0x18002f045  jnz     short loc_18002F04C
0x18002f047  test    r8b, r8b
0x18002f04a  jz      short loc_18002F071
0x18002f04c  mov     [rsp+98h+var_50], rdi
0x18002f051  mov     [rsp+98h+var_60], r13
0x18002f056  mov     [rsp+98h+var_68], 24h ; '$'
0x18002f05d  mov     r9, [rcx+28h]
0x18002f061  mov     rcx, [rcx+10h]
0x18002f065  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f071  mov     rax, [rdi]
0x18002f074  test    rax, rax
0x18002f077  jz      loc_18002F11B
0x18002f07d  mov     rax, [rax]
0x18002f080  sub     rax, rsi
0x18002f083  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f087  ja      loc_18002F11B
0x18002f08d  mov     eax, [rdi+88h]
0x18002f093  cmp     eax, 3E5h
0x18002f098  jnz     short loc_18002F114
0x18002f09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0a1  cmp     rcx, r14
0x18002f0a4  jz      short loc_18002F0B1
0x18002f0a6  cmp     byte ptr [rcx+19h], 3
0x18002f0aa  jb      short loc_18002F0B1
0x18002f0ac  mov     dl, sil
0x18002f0af  jmp     short loc_18002F0B3
0x18002f0b1  xor     dl, dl
0x18002f0b3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002f0ba  setnz   r10b
0x18002f0be  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f0c2  test    dl, dl
0x18002f0c4  jnz     short loc_18002F0CB
0x18002f0c6  test    r10b, r10b
0x18002f0c9  jz      short loc_18002F0FC
0x18002f0cb  mov     rax, [rdi]
0x18002f0ce  test    rax, rax
0x18002f0d1  jz      short loc_18002F0D8
0x18002f0d3  mov     r8, [rax]
0x18002f0d6  jmp     short loc_18002F0DB
0x18002f0d8  mov     r8, rbx
0x18002f0db  mov     [rsp+98h+var_50], r8
0x18002f0e0  mov     [rsp+98h+var_60], r13
0x18002f0e5  mov     [rsp+98h+var_68], 25h ; '%'
0x18002f0ec  mov     r9, [rcx+28h]
0x18002f0f0  mov     r8b, r10b
0x18002f0f3  mov     rcx, [rcx+10h]
0x18002f0f7  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f0fc  mov     rax, [rdi]
0x18002f0ff  test    rax, rax
0x18002f102  jz      short loc_18002F107
0x18002f104  mov     rbx, [rax]
0x18002f107  lea     rdx, [rdi+58h]; lpOverlapped
0x18002f10b  mov     rcx, rbx; hFile
0x18002f10e  call    cs:__imp_CancelIoEx
0x18002f114  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f11b  cmp     rcx, r14
0x18002f11e  jz      short loc_18002F12B
0x18002f120  cmp     byte ptr [rcx+19h], 5
0x18002f124  jb      short loc_18002F12B
0x18002f126  mov     dl, sil
0x18002f129  jmp     short loc_18002F12D
0x18002f12b  xor     dl, dl
0x18002f12d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002f134  setnz   r8b
0x18002f138  test    dl, dl
0x18002f13a  jnz     short loc_18002F141
0x18002f13c  test    r8b, r8b
0x18002f13f  jz      short loc_18002F166
0x18002f141  mov     [rsp+98h+var_50], rdi
0x18002f146  mov     [rsp+98h+var_60], r13
0x18002f14b  mov     [rsp+98h+var_68], 26h ; '&'
0x18002f152  mov     r9, [rcx+28h]
0x18002f156  mov     rcx, [rcx+10h]
0x18002f15a  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f166  cmp     rcx, r14
0x18002f169  jz      short loc_18002F176
0x18002f16b  cmp     byte ptr [rcx+19h], 5
0x18002f16f  jb      short loc_18002F176
0x18002f171  mov     dl, sil
0x18002f174  jmp     short loc_18002F178
0x18002f176  xor     dl, dl
0x18002f178  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002f17f  setnz   r8b
0x18002f183  test    dl, dl
0x18002f185  jnz     short loc_18002F18C
0x18002f187  test    r8b, r8b
0x18002f18a  jz      short loc_18002F1AA
0x18002f18c  mov     [rsp+98h+var_50], rdi
0x18002f191  mov     [rsp+98h+var_60], r13
0x18002f196  mov     [rsp+98h+var_68], 27h ; '''
0x18002f19d  mov     r9, [rcx+28h]
0x18002f1a1  mov     rcx, [rcx+10h]
0x18002f1a5  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f1aa  mov     rcx, [rdi+808h]; hEvent
0x18002f1b1  test    rcx, rcx
0x18002f1b4  jz      short loc_18002F1BC
0x18002f1b6  call    cs:__imp_SetEvent
0x18002f1bc  mov     rbp, [rdi+7F8h]
0x18002f1c3  test    rbp, rbp
0x18002f1c6  jz      short loc_18002F1E2
0x18002f1c8  call    cs:__imp_GetLastError
0x18002f1ce  mov     ebx, eax
0x18002f1d0  mov     rcx, rbp
0x18002f1d3  call    cs:__imp_DafCloseAssociationContext
0x18002f1d9  mov     ecx, ebx; dwErrCode
0x18002f1db  call    cs:__imp_SetLastError
0x18002f1e1  nop
0x18002f1e2  mov     qword ptr [rdi+7F8h], 0
0x18002f1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1f4  cmp     rcx, r14
0x18002f1f7  jz      short loc_18002F204
0x18002f1f9  cmp     byte ptr [rcx+19h], 5
0x18002f1fd  jb      short loc_18002F204
0x18002f1ff  mov     dl, sil
0x18002f202  jmp     short loc_18002F206
0x18002f204  xor     dl, dl
0x18002f206  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f20d  cmp     rax, r12
0x18002f210  setnz   r8b
0x18002f214  test    dl, dl
0x18002f216  jnz     short loc_18002F21D
0x18002f218  test    r8b, r8b
0x18002f21b  jz      short loc_18002F249
0x18002f21d  mov     [rsp+98h+var_50], rdi
0x18002f222  mov     [rsp+98h+var_60], r13
0x18002f227  mov     [rsp+98h+var_68], 28h ; '('
0x18002f22e  mov     r9, [rcx+28h]
0x18002f232  mov     rcx, [rcx+10h]
0x18002f236  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f23b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f242  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f249  cmp     rcx, r14
0x18002f24c  jz      short loc_18002F254
0x18002f24e  cmp     byte ptr [rcx+19h], 5
0x18002f252  jnb     short loc_18002F257
0x18002f254  xor     sil, sil
0x18002f257  cmp     rax, r12
0x18002f25a  setnz   r8b
0x18002f25e  test    sil, sil
0x18002f261  jnz     short loc_18002F268
0x18002f263  test    r8b, r8b
0x18002f266  jz      short loc_18002F291
0x18002f268  mov     [rsp+98h+var_48], 0
0x18002f270  mov     [rsp+98h+var_50], rdi
0x18002f275  mov     [rsp+98h+var_60], r13
0x18002f27a  mov     [rsp+98h+var_68], 23h ; '#'
0x18002f281  mov     r9, [rcx+28h]
0x18002f285  mov     dl, sil
0x18002f288  mov     rcx, [rcx+10h]
0x18002f28c  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002f291  xor     eax, eax
0x18002f293  add     rsp, 60h
0x18002f297  pop     r14
0x18002f299  pop     r13
0x18002f29b  pop     r12
0x18002f29d  pop     rdi
0x18002f29e  pop     rsi
0x18002f29f  pop     rbp
0x18002f2a0  pop     rbx
0x18002f2a1  retn
```
