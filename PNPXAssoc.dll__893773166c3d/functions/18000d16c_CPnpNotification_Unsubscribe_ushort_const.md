# CPnpNotification::Unsubscribe(ushort const *)

- ea: `0x18000d16c`
- end: `0x18000d29f`
- name: `?Unsubscribe@CPnpNotification@@QEAAJPEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(CPnpNotification *__hidden this, wchar_t *String1)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180009990`
- `0x18000a28c`
- `0x18000ccec`

## callees

- `0x18000bce4`
- `0x18000bd30`
- `0x18000c33c`
- `0x18000d16c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d219`
- `msvcrt!_wcsicmp` at `0x18000d219`
- `KERNEL32!LeaveCriticalSection` at `0x18000d23f`
- `KERNEL32!LeaveCriticalSection` at `0x18000d23f`
- `KERNEL32!EnterCriticalSection` at `0x18000d1fa`
- `KERNEL32!EnterCriticalSection` at `0x18000d1fa`

## pseudocode

```c
__int64 __fastcall CPnpNotification::Unsubscribe(CPnpNotification *this, wchar_t *String1)
{
  _QWORD *v4; // rcx
  struct _NOTIFICATION_ITEM *v6; // rbp
  char *v7; // rsi
  char *v8; // rdi
  int v9; // eax
  char *v10; // rcx
  char **v11; // rax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( String1 )
  {
    v6 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v7 = (char *)this + 128;
    v8 = (char *)*((_QWORD *)this + 16);
    if ( v8 != (char *)this + 128 )
    {
      while ( 1 )
      {
        v6 = (struct _NOTIFICATION_ITEM *)v8;
        v9 = _wcsicmp(String1, *((const wchar_t **)v8 + 3));
        v10 = *(char **)v8;
        if ( !v9 )
          break;
        v8 = *(char **)v8;
        if ( v10 == v7 )
          goto LABEL_14;
      }
      v11 = (char **)*((_QWORD *)v8 + 1);
      *v11 = v10;
      *((_QWORD *)v10 + 1) = v11;
    }
LABEL_14:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    if ( v8 != v7 && v6 )
      CPnpNotification::FreeNotificationItem(this, v6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    return 0;
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_sqd(v4[2], 40, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000d16c  push    rbx
0x18000d16e  push    rbp
0x18000d16f  push    rsi
0x18000d170  push    rdi
0x18000d171  push    r12
0x18000d173  push    r14
0x18000d175  push    r15
0x18000d177  sub     rsp, 30h
0x18000d17b  mov     r14, rdx
0x18000d17e  mov     rbx, rcx
0x18000d181  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d188  lea     r12, WPP_GLOBAL_Control
0x18000d18f  cmp     rcx, r12
0x18000d192  jz      short loc_18000D1BB
0x18000d194  cmp     byte ptr [rcx+19h], 4
0x18000d198  jb      short loc_18000D1BB
0x18000d19a  mov     rcx, [rcx+10h]
0x18000d19e  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000d1a5  mov     edx, 27h ; '''
0x18000d1aa  mov     [rsp+68h+var_48], rbx
0x18000d1af  call    WPP_SF_sq
0x18000d1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1bb  test    r14, r14
0x18000d1be  jnz     short loc_18000D1F4
0x18000d1c0  mov     edi, 80070057h
0x18000d1c5  cmp     rcx, r12
0x18000d1c8  jz      short loc_18000D1ED
0x18000d1ca  cmp     byte ptr [rcx+19h], 2
0x18000d1ce  jb      short loc_18000D1ED
0x18000d1d0  mov     rcx, [rcx+10h]
0x18000d1d4  lea     edx, [r14+28h]
0x18000d1d8  mov     [rsp+68h+var_40], edi
0x18000d1dc  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000d1e3  mov     [rsp+68h+var_48], rbx
0x18000d1e8  call    WPP_SF_sqd
0x18000d1ed  mov     eax, edi
0x18000d1ef  jmp     loc_18000D290
0x18000d1f4  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000d1f8  xor     ebp, ebp
0x18000d1fa  call    cs:__imp_EnterCriticalSection
0x18000d200  lea     rsi, [rbx+80h]
0x18000d207  mov     rdi, [rsi]
0x18000d20a  cmp     rdi, rsi
0x18000d20d  jz      short loc_18000D23B
0x18000d20f  mov     rdx, [rdi+18h]; String2
0x18000d213  mov     rcx, r14; String1
0x18000d216  mov     rbp, rdi
0x18000d219  call    cs:__imp__wcsicmp
0x18000d21f  mov     rcx, [rdi]
0x18000d222  test    eax, eax
0x18000d224  jz      short loc_18000D230
0x18000d226  mov     rdi, rcx
0x18000d229  cmp     rcx, rsi
0x18000d22c  jnz     short loc_18000D20F
0x18000d22e  jmp     short loc_18000D23B
0x18000d230  mov     rax, [rdi+8]
0x18000d234  mov     [rax], rcx
0x18000d237  mov     [rcx+8], rax
0x18000d23b  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000d23f  call    cs:__imp_LeaveCriticalSection
0x18000d245  cmp     rdi, rsi
0x18000d248  jz      short loc_18000D25A
0x18000d24a  test    rbp, rbp
0x18000d24d  jz      short loc_18000D25A
0x18000d24f  mov     rdx, rbp; struct _NOTIFICATION_ITEM *
0x18000d252  mov     rcx, rbx; this
0x18000d255  call    ?FreeNotificationItem@CPnpNotification@@IEAAXPEAU_NOTIFICATION_ITEM@@@Z; CPnpNotification::FreeNotificationItem(_NOTIFICATION_ITEM *)
0x18000d25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d261  cmp     rcx, r12
0x18000d264  jz      short loc_18000D28E
0x18000d266  cmp     byte ptr [rcx+19h], 4
0x18000d26a  jb      short loc_18000D28E
0x18000d26c  mov     rcx, [rcx+10h]
0x18000d270  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000d277  mov     edx, 29h ; ')'
0x18000d27c  mov     [rsp+68h+var_40], 0
0x18000d284  mov     [rsp+68h+var_48], rbx
0x18000d289  call    WPP_SF_sqd
0x18000d28e  xor     eax, eax
0x18000d290  add     rsp, 30h
0x18000d294  pop     r15
0x18000d296  pop     r14
0x18000d298  pop     r12
0x18000d29a  pop     rdi
0x18000d29b  pop     rsi
0x18000d29c  pop     rbp
0x18000d29d  pop     rbx
0x18000d29e  retn
```
