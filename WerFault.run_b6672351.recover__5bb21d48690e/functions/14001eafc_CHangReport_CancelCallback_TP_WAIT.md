# CHangReport::CancelCallback(_TP_WAIT *)

- ea: `0x14001eafc`
- end: `0x14001ecbb`
- name: `?CancelCallback@CHangReport@@AEAAXPEAU_TP_WAIT@@@Z`
- size: `447`
- prototype: `void __fastcall(CHangReport *__hidden this, struct _TP_WAIT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140020f60`

## callees

- `0x140014ee4`
- `0x14001eafc`
- `0x1400207c4`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001ec91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001ec91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ec65`
- `wer!WerpReportCancel` at `0x14001eca0`
- `wer!WerpReportCancel` at `0x14001eca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHangReport::CancelCallback(struct _TP_WAIT **this, struct _TP_WAIT *a2)
{
  CUserModeHangReport *v4; // rcx
  PTP_WAIT *v5; // rbx
  __int64 v6; // rdx
  struct _TP_WAIT *v7; // r14
  struct _TP_WAIT *v8; // rcx
  struct _TP_WAIT *v9; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h]

  CHangReport::Lock(this, &lpCriticalSection, L"CHangReport::CancelCallback");
  if ( a2 != this[3094] )
  {
    v5 = this + 3093;
    if ( a2 == this[3093] )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_18;
      }
      v6 = 12;
    }
    else if ( a2 == this[3092] )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_18;
      }
      v6 = 13;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_18;
      }
      v6 = 14;
    }
    WPP_SF_(*((_QWORD *)v4 + 2), v6, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = this + 3093;
LABEL_18:
  v7 = this[3055];
  if ( v4 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v4 + 2), 15, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
  *((_DWORD *)this + 15) = 1;
  v8 = this[3094];
  if ( v8 )
    SetThreadpoolWait(v8, 0, 0);
  if ( *v5 )
    SetThreadpoolWait(*v5, 0, 0);
  v9 = this[3092];
  if ( v9 )
    SetThreadpoolWait(v9, 0, 0);
  (*((void (__fastcall **)(struct _TP_WAIT **, struct _TP_WAIT *))*this + 7))(this, a2);
  if ( !v11 )
    __int2c();
  LeaveCriticalSection(lpCriticalSection);
  WerpReportCancel(v7);
}

```

## disassembly

```asm
0x14001eafc  push    rbx
0x14001eafe  push    rbp
0x14001eaff  push    rsi
0x14001eb00  push    rdi
0x14001eb01  push    r14
0x14001eb03  push    r15
0x14001eb05  sub     rsp, 38h
0x14001eb09  mov     rbp, rdx
0x14001eb0c  mov     rdi, rcx
0x14001eb0f  lea     r8, aChangreportCan; "CHangReport::CancelCallback"
0x14001eb16  lea     rdx, [rsp+68h+lpCriticalSection]
0x14001eb1b  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001eb20  nop
0x14001eb21  lea     r15, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001eb28  cmp     rbp, [rdi+60B0h]
0x14001eb2f  jnz     short loc_14001EB6E
0x14001eb31  lea     rsi, WPP_GLOBAL_Control
0x14001eb38  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb3f  cmp     rcx, rsi
0x14001eb42  jz      short loc_14001EB62
0x14001eb44  test    byte ptr [rcx+1Ch], 4
0x14001eb48  jz      short loc_14001EB62
0x14001eb4a  mov     edx, 0Bh
0x14001eb4f  mov     r8, r15
0x14001eb52  mov     rcx, [rcx+10h]
0x14001eb56  call    WPP_SF_
0x14001eb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb62  lea     rbx, [rdi+60A8h]
0x14001eb69  jmp     loc_14001EBF4
0x14001eb6e  lea     rbx, [rdi+60A8h]
0x14001eb75  cmp     rbp, [rbx]
0x14001eb78  jnz     short loc_14001EB9A
0x14001eb7a  lea     rsi, WPP_GLOBAL_Control
0x14001eb81  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb88  cmp     rcx, rsi
0x14001eb8b  jz      short loc_14001EBF4
0x14001eb8d  test    byte ptr [rcx+1Ch], 4
0x14001eb91  jz      short loc_14001EBF4
0x14001eb93  mov     edx, 0Ch
0x14001eb98  jmp     short loc_14001EBE1
0x14001eb9a  cmp     rbp, [rdi+60A0h]
0x14001eba1  jnz     short loc_14001EBC3
0x14001eba3  lea     rsi, WPP_GLOBAL_Control
0x14001ebaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebb1  cmp     rcx, rsi
0x14001ebb4  jz      short loc_14001EBF4
0x14001ebb6  test    byte ptr [rcx+1Ch], 4
0x14001ebba  jz      short loc_14001EBF4
0x14001ebbc  mov     edx, 0Dh
0x14001ebc1  jmp     short loc_14001EBE1
0x14001ebc3  lea     rsi, WPP_GLOBAL_Control
0x14001ebca  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebd1  cmp     rcx, rsi
0x14001ebd4  jz      short loc_14001EBF4
0x14001ebd6  test    byte ptr [rcx+1Ch], 1
0x14001ebda  jz      short loc_14001EBF4
0x14001ebdc  mov     edx, 0Eh
0x14001ebe1  mov     r8, r15
0x14001ebe4  mov     rcx, [rcx+10h]
0x14001ebe8  call    WPP_SF_
0x14001ebed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebf4  mov     r14, [rdi+5F78h]
0x14001ebfb  cmp     rcx, rsi
0x14001ebfe  jz      short loc_14001EC17
0x14001ec00  test    byte ptr [rcx+1Ch], 8
0x14001ec04  jz      short loc_14001EC17
0x14001ec06  mov     edx, 0Fh
0x14001ec0b  mov     r8, r15
0x14001ec0e  mov     rcx, [rcx+10h]
0x14001ec12  call    WPP_SF_
0x14001ec17  mov     dword ptr [rdi+3Ch], 1
0x14001ec1e  mov     rcx, [rdi+60B0h]; pwa
0x14001ec25  test    rcx, rcx
0x14001ec28  jz      short loc_14001EC3B
0x14001ec2a  xor     r8d, r8d; pftTimeout
0x14001ec2d  xor     edx, edx; h
0x14001ec2f  call    cs:__imp_SetThreadpoolWait
0x14001ec36  nop     dword ptr [rax+rax+00h]
0x14001ec3b  mov     rcx, [rbx]; pwa
0x14001ec3e  test    rcx, rcx
0x14001ec41  jz      short loc_14001EC54
0x14001ec43  xor     r8d, r8d; pftTimeout
0x14001ec46  xor     edx, edx; h
0x14001ec48  call    cs:__imp_SetThreadpoolWait
0x14001ec4f  nop     dword ptr [rax+rax+00h]
0x14001ec54  mov     rcx, [rdi+60A0h]; pwa
0x14001ec5b  test    rcx, rcx
0x14001ec5e  jz      short loc_14001EC71
0x14001ec60  xor     r8d, r8d; pftTimeout
0x14001ec63  xor     edx, edx; h
0x14001ec65  call    cs:__imp_SetThreadpoolWait
0x14001ec6c  nop     dword ptr [rax+rax+00h]
0x14001ec71  mov     rax, [rdi]
0x14001ec74  mov     rdx, rbp
0x14001ec77  mov     rcx, rdi
0x14001ec7a  mov     rax, [rax+38h]
0x14001ec7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ec83  cmp     [rsp+68h+var_40], 0
0x14001ec88  jnz     short loc_14001EC8C
0x14001ec8a  int     2Ch; Windows NT - assertion failure
0x14001ec8c  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x14001ec91  call    cs:__imp_LeaveCriticalSection
0x14001ec98  nop     dword ptr [rax+rax+00h]
0x14001ec9d  mov     rcx, r14
0x14001eca0  call    cs:__imp_WerpReportCancel
0x14001eca7  nop     dword ptr [rax+rax+00h]
0x14001ecac  nop
0x14001ecad  add     rsp, 38h
0x14001ecb1  pop     r15
0x14001ecb3  pop     r14
0x14001ecb5  pop     rdi
0x14001ecb6  pop     rsi
0x14001ecb7  pop     rbp
0x14001ecb8  pop     rbx
0x14001ecb9  retn
```
