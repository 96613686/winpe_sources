# HCI_CompleteAclRdChain(_BIP *)

- ea: `0x14002c8b0`
- end: `0x14002ca3b`
- name: `?HCI_CompleteAclRdChain@@YAXPEAU_BIP@@@Z`
- size: `395`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x14002c8b0`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c9c5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c9c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c9af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c9af`

## string_xrefs

- `0x14002c98d`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`

## pseudocode

```c
void __fastcall HCI_CompleteAclRdChain(char *Entry)
{
  char v2; // si
  char v3; // dl
  __int16 DeviceType; // ax
  char *v5; // rbx
  char *v6; // rdx
  char **v7; // r8
  char *v8; // rcx
  char *v9; // rax
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r8d
  __int16 v13; // ax

  v2 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      15,
      (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
      (char)Entry);
  v5 = (char *)*((_QWORD *)Entry + 9);
  while ( v5 != Entry + 72 )
  {
    v6 = *(char **)v5;
    if ( *(char **)(*(_QWORD *)v5 + 8LL) != v5 || (v7 = (char **)*((_QWORD *)v5 + 1), *v7 != v5) )
      __fastfail(3u);
    *v7 = v6;
    v8 = v5 - 72;
    *((_QWORD *)v6 + 1) = v7;
    v9 = v5;
    *((_QWORD *)v5 + 1) = v5;
    v5 = v6;
    *(_QWORD *)v9 = v9;
    *((_DWORD *)v8 + 3) = *((_DWORD *)Entry + 3);
    (*((void (**)(void))v8 + 18))();
  }
  v10 = *(_QWORD *)(*((_QWORD *)Entry + 19) + 80LL);
  if ( v10 )
    RefObj_ReleaseEx(
      v10 + 8,
      HCI_GetConnectionOrZombieFromHandleLocked,
      166,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclread.cpp");
  ExFreePoolWithTag(*((PVOID *)Entry + 19), 0);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(*(_QWORD *)Entry + 112LL), Entry);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v13 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v13 )
  {
    LOBYTE(v11) = v2;
    LOBYTE(v12) = v13 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v12,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      16,
      (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids);
  }
}

```

## disassembly

```asm
0x14002c8b0  push    rbx
0x14002c8b2  push    rbp
0x14002c8b3  push    rsi
0x14002c8b4  push    rdi
0x14002c8b5  push    r12
0x14002c8b7  push    r14
0x14002c8b9  sub     rsp, 58h
0x14002c8bd  mov     rdi, rcx
0x14002c8c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c8c7  xor     ebp, ebp
0x14002c8c9  mov     sil, 1
0x14002c8cc  mov     eax, [rcx+2Ch]
0x14002c8cf  test    al, 2
0x14002c8d1  jz      short loc_14002C8DC
0x14002c8d3  cmp     byte ptr [rcx+29h], 5
0x14002c8d7  mov     dl, sil
0x14002c8da  jnb     short loc_14002C8DF
0x14002c8dc  mov     dl, bpl
0x14002c8df  movzx   eax, word ptr [rcx+48h]
0x14002c8e3  lea     r12, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002c8ea  test    ax, ax
0x14002c8ed  setnz   r8b
0x14002c8f1  test    dl, dl
0x14002c8f3  jnz     short loc_14002C8FA
0x14002c8f5  test    ax, ax
0x14002c8f8  jz      short loc_14002C925
0x14002c8fa  mov     r9, [rcx+40h]
0x14002c8fe  mov     rcx, [rcx+18h]
0x14002c902  mov     [rsp+88h+var_48], rdi
0x14002c907  mov     [rsp+88h+var_50], r12
0x14002c90c  mov     [rsp+88h+var_58], 0Fh
0x14002c913  mov     [rsp+88h+var_60], 2
0x14002c91b  mov     [rsp+88h+var_68], 5
0x14002c920  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002c925  lea     r14, [rdi+48h]
0x14002c929  mov     rbx, [r14]
0x14002c92c  jmp     short loc_14002C974
0x14002c92e  mov     rdx, [rbx]
0x14002c931  cmp     [rdx+8], rbx
0x14002c935  jnz     loc_14002CA34
0x14002c93b  lea     r9, [rbx+8]
0x14002c93f  mov     r8, [r9]
0x14002c942  cmp     [r8], rbx
0x14002c945  jnz     loc_14002CA34
0x14002c94b  mov     [r8], rdx
0x14002c94e  lea     rcx, [rbx-48h]
0x14002c952  mov     [rdx+8], r8
0x14002c956  mov     rax, rbx
0x14002c959  mov     [r9], rax
0x14002c95c  mov     rbx, rdx
0x14002c95f  mov     [rax], rax
0x14002c962  mov     eax, [rdi+0Ch]
0x14002c965  mov     [rcx+0Ch], eax
0x14002c968  mov     rax, [rcx+90h]
0x14002c96f  call    _guard_dispatch_icall
0x14002c974  cmp     rbx, r14
0x14002c977  jnz     short loc_14002C92E
0x14002c979  mov     rax, [rdi+98h]
0x14002c980  mov     rcx, [rax+50h]
0x14002c984  test    rcx, rcx
0x14002c987  jz      short loc_14002C9A6
0x14002c989  add     rcx, 8
0x14002c98d  lea     r9, aOnecoreDrivers_52; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002c994  mov     r8d, 0A6h
0x14002c99a  lea     rdx, ?HCI_GetConnectionOrZombieFromHandleLocked@@YAPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@G@Z; HCI_GetConnectionOrZombieFromHandleLocked(HCI_INTERFACE *,ushort)
0x14002c9a1  call    RefObj_ReleaseEx
0x14002c9a6  mov     rcx, [rdi+98h]; P
0x14002c9ad  xor     edx, edx; Tag
0x14002c9af  call    cs:__imp_ExFreePoolWithTag
0x14002c9b6  nop     dword ptr [rax+rax+00h]
0x14002c9bb  mov     rcx, [rdi]
0x14002c9be  mov     rdx, rdi; Entry
0x14002c9c1  add     rcx, 70h ; 'p'; Lookaside
0x14002c9c5  call    cs:__imp_ExFreeToLookasideListEx
0x14002c9cc  nop     dword ptr [rax+rax+00h]
0x14002c9d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c9d8  mov     eax, [rcx+2Ch]
0x14002c9db  test    al, 2
0x14002c9dd  jz      short loc_14002C9E5
0x14002c9df  cmp     byte ptr [rcx+29h], 5
0x14002c9e3  jnb     short loc_14002C9E8
0x14002c9e5  mov     sil, bpl
0x14002c9e8  movzx   eax, word ptr [rcx+48h]
0x14002c9ec  test    ax, ax
0x14002c9ef  setnz   r8b
0x14002c9f3  test    sil, sil
0x14002c9f6  jnz     short loc_14002C9FD
0x14002c9f8  test    ax, ax
0x14002c9fb  jz      short loc_14002CA26
0x14002c9fd  mov     r9, [rcx+40h]
0x14002ca01  mov     dl, sil
0x14002ca04  mov     rcx, [rcx+18h]
0x14002ca08  mov     [rsp+88h+var_50], r12
0x14002ca0d  mov     [rsp+88h+var_58], 10h
0x14002ca14  mov     [rsp+88h+var_60], 2
0x14002ca1c  mov     [rsp+88h+var_68], 5
0x14002ca21  call    WPP_RECORDER_AND_TRACE_SF_
0x14002ca26  add     rsp, 58h
0x14002ca2a  pop     r14
0x14002ca2c  pop     r12
0x14002ca2e  pop     rdi
0x14002ca2f  pop     rsi
0x14002ca30  pop     rbp
0x14002ca31  pop     rbx
0x14002ca32  retn
0x14002ca34  mov     ecx, 3
0x14002ca39  int     29h; Win8: RtlFailFast(ecx)
```
