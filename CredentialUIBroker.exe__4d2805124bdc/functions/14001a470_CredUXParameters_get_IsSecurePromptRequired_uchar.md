# CredUXParameters::get_IsSecurePromptRequired(uchar *)

- ea: `0x14001a470`
- end: `0x14001a505`
- name: `?get_IsSecurePromptRequired@CredUXParameters@@UEAAJPEAE@Z`
- size: `149`
- prototype: `__int64 __fastcall(CredUXParameters *this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a470`
- `0x14001f010`

## string_xrefs

- `0x14001a4b7`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_IsSecurePromptRequired(CredUXParameters *this, unsigned __int8 *a2)
{
  char v2; // r8
  __int64 v4; // rcx
  int v6; // eax
  unsigned int v7; // edi
  unsigned __int8 v9; // al
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v12; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  *a2 = 0;
  v12 = 0;
  v4 = *((_QWORD *)this + 24);
  if ( v4 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 72LL))(v4, &v12);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v6,
        v10);
      return v7;
    }
    v2 = v12;
  }
  if ( (*((_BYTE *)this + 72) & 2) != 0
    || (v9 = 1, (*((_BYTE *)this + 68) & 1) != 0)
    || !v2 && (*((_DWORD *)this + 17) & 0x1000) == 0 )
  {
    v9 = 0;
  }
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x14001a470  mov     r11, rsp
0x14001a473  mov     [r11+10h], rbx
0x14001a477  mov     [r11+18h], rsi
0x14001a47b  push    rdi; int
0x14001a47c  sub     rsp, 20h
0x14001a480  xor     r8b, r8b
0x14001a483  mov     byte ptr [rdx], 0
0x14001a486  mov     rbx, rcx
0x14001a489  mov     [r11+8], r8b
0x14001a48d  mov     rcx, [rcx+0C0h]
0x14001a494  mov     rsi, rdx
0x14001a497  test    rcx, rcx
0x14001a49a  jz      short loc_14001A4D4
0x14001a49c  mov     rax, [rcx]
0x14001a49f  lea     rdx, [r11+8]
0x14001a4a3  mov     rax, [rax+48h]
0x14001a4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4ac  mov     edi, eax
0x14001a4ae  test    eax, eax
0x14001a4b0  jns     short loc_14001A4CF
0x14001a4b2  mov     rcx, [rsp+28h]; this
0x14001a4b7  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a4be  mov     r9d, eax; char *
0x14001a4c1  mov     edx, 130h; void *
0x14001a4c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a4cb  mov     eax, edi
0x14001a4cd  jmp     short loc_14001A4F5
0x14001a4cf  mov     r8b, [rsp+28h+arg_0]
0x14001a4d4  test    byte ptr [rbx+48h], 2
0x14001a4d8  jnz     short loc_14001A4EF
0x14001a4da  mov     al, 1
0x14001a4dc  test    [rbx+44h], al
0x14001a4df  jnz     short loc_14001A4EF
0x14001a4e1  test    r8b, r8b
0x14001a4e4  jnz     short loc_14001A4F1
0x14001a4e6  test    dword ptr [rbx+44h], 1000h
0x14001a4ed  jnz     short loc_14001A4F1
0x14001a4ef  xor     eax, eax
0x14001a4f1  mov     [rsi], al
0x14001a4f3  xor     eax, eax
0x14001a4f5  mov     rbx, [rsp+28h+arg_8]
0x14001a4fa  mov     rsi, [rsp+28h+arg_10]
0x14001a4ff  add     rsp, 20h
0x14001a503  pop     rdi
0x14001a504  retn
```
