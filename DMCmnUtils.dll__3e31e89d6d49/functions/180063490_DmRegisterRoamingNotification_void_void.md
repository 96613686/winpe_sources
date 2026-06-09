# DmRegisterRoamingNotification(void *,void * *)

- ea: `0x180063490`
- end: `0x18006356a`
- name: `?DmRegisterRoamingNotification@@YAJPEAXPEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180063490`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x180063519`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x180063519`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180063553`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180063553`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800634cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800634cc`

## pseudocode

```c
__int64 __fastcall DmRegisterRoamingNotification(void *a1, void **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v7; // [rsp+58h] [rbp+10h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF
  void *v9; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  v7 = 0;
  v9 = 0;
  v8 = 0;
  v4 = 1;
  v5 = WwanOpenHandle(1, 0, &v7, &v9);
  if ( v5 == 1062 )
  {
    *a2 = (void *)-1LL;
    goto LABEL_10;
  }
  if ( v5 )
  {
    if ( v5 <= 0 )
    {
      v4 = v5;
      goto LABEL_10;
    }
LABEL_8:
    v4 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_10;
  }
  v5 = WwanRegisterNotification(v9, 2, &WwanNotificationCallback, a1, 0, &v8);
  v4 = v5;
  if ( v5 )
  {
    if ( v5 <= 0 )
      goto LABEL_10;
    goto LABEL_8;
  }
  v4 = 0;
  *a2 = v9;
  v9 = 0;
LABEL_10:
  if ( v9 )
    WwanCloseHandle(v9, 0);
  return v4;
}

```

## disassembly

```asm
0x180063490  mov     rax, rsp
0x180063493  push    rbx
0x180063494  push    rsi
0x180063495  push    rdi
0x180063496  sub     rsp, 30h
0x18006349a  mov     rdi, rdx
0x18006349d  mov     qword ptr [rdx], 0
0x1800634a4  xor     edx, edx
0x1800634a6  mov     dword ptr [rax+10h], 0
0x1800634ad  mov     rsi, rcx
0x1800634b0  mov     qword ptr [rax+20h], 0
0x1800634b8  lea     r9, [rax+20h]
0x1800634bc  mov     dword ptr [rax+18h], 0
0x1800634c3  lea     r8, [rax+10h]
0x1800634c7  lea     ebx, [rdx+1]
0x1800634ca  mov     ecx, ebx
0x1800634cc  call    cs:__imp_WwanOpenHandle
0x1800634d3  nop     dword ptr [rax+rax+00h]
0x1800634d8  cmp     eax, 426h
0x1800634dd  jnz     short loc_1800634E8
0x1800634df  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800634e6  jmp     short loc_180063547
0x1800634e8  test    eax, eax
0x1800634ea  jz      short loc_1800634F2
0x1800634ec  jg      short loc_18006352D
0x1800634ee  mov     ebx, eax
0x1800634f0  jmp     short loc_180063547
0x1800634f2  mov     rcx, [rsp+48h+arg_18]
0x1800634f7  lea     rax, [rsp+48h+arg_10]
0x1800634fc  mov     [rsp+48h+var_20], rax
0x180063501  lea     r8, WwanNotificationCallback
0x180063508  mov     r9, rsi
0x18006350b  mov     [rsp+48h+var_28], 0
0x180063514  mov     edx, 2
0x180063519  call    cs:__imp_WwanRegisterNotification
0x180063520  nop     dword ptr [rax+rax+00h]
0x180063525  mov     ebx, eax
0x180063527  test    eax, eax
0x180063529  jz      short loc_180063538
0x18006352b  jle     short loc_180063547
0x18006352d  movzx   ebx, ax
0x180063530  or      ebx, 80070000h
0x180063536  jmp     short loc_180063547
0x180063538  mov     rcx, [rsp+48h+arg_18]
0x18006353d  xor     ebx, ebx
0x18006353f  mov     [rdi], rcx
0x180063542  mov     [rsp+48h+arg_18], rbx
0x180063547  mov     rcx, [rsp+48h+arg_18]
0x18006354c  test    rcx, rcx
0x18006354f  jz      short loc_18006355F
0x180063551  xor     edx, edx
0x180063553  call    cs:__imp_WwanCloseHandle
0x18006355a  nop     dword ptr [rax+rax+00h]
0x18006355f  mov     eax, ebx
0x180063561  add     rsp, 30h
0x180063565  pop     rdi
0x180063566  pop     rsi
0x180063567  pop     rbx
0x180063568  retn
```
