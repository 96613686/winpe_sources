# BamUserSettingsGet

- ea: `0x140012c84`
- end: `0x140012e51`
- name: `BamUserSettingsGet`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000bea0`
- `0x14001474c`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x140011a98`
- `0x140011b44`
- `0x140012c84`
- `0x140012e58`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140012d6b`
- `ntoskrnl!ZwClose` at `0x140012d6b`

## pseudocode

```c
__int64 __fastcall BamUserSettingsGet(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        char a3,
        _DWORD *a4,
        _QWORD *a5)
{
  HANDLE v5; // rdi
  int v7; // r12d
  NTSTATUS Entry; // ebx
  int v11; // eax
  HANDLE Handle; // [rsp+38h] [rbp-99h] BYREF
  int v15; // [rsp+40h] [rbp-91h] BYREF
  __int128 v16; // [rsp+48h] [rbp-89h] BYREF
  __int64 v17; // [rsp+58h] [rbp-79h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+60h] [rbp-71h] BYREF
  _DWORD *v19; // [rsp+80h] [rbp-51h]
  __int64 v20; // [rsp+88h] [rbp-49h]
  wchar_t *Buffer; // [rsp+90h] [rbp-41h]
  _DWORD v22[2]; // [rsp+98h] [rbp-39h] BYREF
  _DWORD *v23; // [rsp+A0h] [rbp-31h]
  __int64 v24; // [rsp+A8h] [rbp-29h]
  wchar_t *v25; // [rsp+B0h] [rbp-21h]
  _DWORD v26[2]; // [rsp+B8h] [rbp-19h] BYREF
  int *v27; // [rsp+C0h] [rbp-11h]
  __int64 v28; // [rsp+C8h] [rbp-9h]
  HANDLE *p_Handle; // [rsp+D0h] [rbp-1h]
  __int64 v30; // [rsp+D8h] [rbp+7h]

  v5 = 0;
  v17 = 0;
  v7 = 3;
  Handle = 0;
  v16 = 0;
  if ( BampUserSettingsContext )
  {
    if ( a1 && a2 && a4 )
    {
      v11 = BampUserSettingsOpenUserKey(a1, 0, &Handle);
      v5 = Handle;
      Entry = v11;
      if ( v11 >= 0 )
      {
        Entry = BampUserSettingsReadEntry(Handle, a2, (__int64)&v16);
        if ( Entry >= 0 )
        {
          v7 = DWORD2(v16);
          *a4 = DWORD2(v16);
          if ( a5 )
            *a5 = v16;
          if ( !a3 || (Entry = BampUserSettingsTouchEntry(v5, a2, &v16), Entry >= 0) )
            Entry = 0;
        }
      }
    }
    else
    {
      Entry = -1073741811;
    }
    if ( v5 )
      ZwClose(v5);
  }
  else
  {
    Entry = -1073741823;
  }
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v20 = 2;
    v19 = v22;
    Buffer = a1->Buffer;
    v22[0] = a1->Length;
    v23 = v26;
    v25 = a2->Buffer;
    v26[0] = a2->Length;
    v27 = &v15;
    p_Handle = &Handle;
    v22[1] = 0;
    v24 = 2;
    v26[1] = 0;
    v15 = v7;
    v28 = 4;
    LODWORD(Handle) = Entry;
    v30 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140007010, (unsigned __int8 *)word_1400058A2, 0, 0, 8u, &v18);
  }
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x140012c84  mov     [rsp-8+arg_10], rbx
0x140012c89  push    rbp
0x140012c8a  push    rsi
0x140012c8b  push    rdi
0x140012c8c  push    r12
0x140012c8e  push    r13
0x140012c90  push    r14
0x140012c92  push    r15
0x140012c94  lea     rbp, [rsp-1Fh]
0x140012c99  sub     rsp, 0F0h
0x140012ca0  mov     rax, cs:__security_cookie
0x140012ca7  xor     rax, rsp
0x140012caa  mov     [rbp+4Fh+var_40], rax
0x140012cae  mov     r15, [rbp+4Fh+arg_20]
0x140012cb2  xor     eax, eax
0x140012cb4  xor     edi, edi
0x140012cb6  mov     [rsp+120h+var_F0], r8b
0x140012cbb  cmp     qword ptr cs:BampUserSettingsContext, rax
0x140012cc2  xorps   xmm0, xmm0
0x140012cc5  mov     r14, r9
0x140012cc8  mov     [rbp+4Fh+var_C8], rax
0x140012ccc  lea     r12d, [rax+3]
0x140012cd0  mov     [rsp+120h+Handle], rdi
0x140012cd5  mov     rsi, rdx
0x140012cd8  mov     r13, rcx
0x140012cdb  movups  [rsp+120h+var_D8], xmm0
0x140012ce0  jnz     short loc_140012CEC
0x140012ce2  mov     ebx, 0C0000001h
0x140012ce7  jmp     loc_140012D77
0x140012cec  test    r13, r13
0x140012cef  jz      short loc_140012D5E
0x140012cf1  test    rsi, rsi
0x140012cf4  jz      short loc_140012D5E
0x140012cf6  test    r14, r14
0x140012cf9  jz      short loc_140012D5E
0x140012cfb  lea     r8, [rsp+120h+Handle]
0x140012d00  xor     edx, edx
0x140012d02  call    BampUserSettingsOpenUserKey
0x140012d07  mov     rdi, [rsp+120h+Handle]
0x140012d0c  mov     ebx, eax
0x140012d0e  test    eax, eax
0x140012d10  js      short loc_140012D63
0x140012d12  lea     r8, [rsp+120h+var_D8]
0x140012d17  mov     rdx, rsi
0x140012d1a  mov     rcx, rdi
0x140012d1d  call    BampUserSettingsReadEntry
0x140012d22  mov     ebx, eax
0x140012d24  test    eax, eax
0x140012d26  js      short loc_140012D63
0x140012d28  mov     r12d, dword ptr [rsp+120h+var_D8+8]
0x140012d2d  mov     [r14], r12d
0x140012d30  test    r15, r15
0x140012d33  jz      short loc_140012D3D
0x140012d35  mov     rax, qword ptr [rsp+120h+var_D8]
0x140012d3a  mov     [r15], rax
0x140012d3d  cmp     [rsp+120h+var_F0], 0
0x140012d42  jz      short loc_140012D5A
0x140012d44  lea     r8, [rsp+120h+var_D8]
0x140012d49  mov     rdx, rsi
0x140012d4c  mov     rcx, rdi
0x140012d4f  call    BampUserSettingsTouchEntry
0x140012d54  mov     ebx, eax
0x140012d56  test    eax, eax
0x140012d58  js      short loc_140012D63
0x140012d5a  xor     ebx, ebx
0x140012d5c  jmp     short loc_140012D63
0x140012d5e  mov     ebx, 0C000000Dh
0x140012d63  test    rdi, rdi
0x140012d66  jz      short loc_140012D77
0x140012d68  mov     rcx, rdi; Handle
0x140012d6b  call    cs:__imp_ZwClose
0x140012d72  nop     dword ptr [rax+rax+00h]
0x140012d77  mov     eax, cs:dword_140007010
0x140012d7d  cmp     eax, 5
0x140012d80  jbe     loc_140012E27
0x140012d86  lea     rax, [rbp+4Fh+var_88]
0x140012d8a  mov     [rbp+4Fh+var_98], 2
0x140012d92  mov     [rbp+4Fh+var_A0], rax
0x140012d96  lea     rdx, word_1400058A2
0x140012d9d  mov     rax, [r13+8]
0x140012da1  lea     rcx, dword_140007010
0x140012da8  mov     [rbp+4Fh+var_90], rax
0x140012dac  xor     r9d, r9d
0x140012daf  movzx   eax, word ptr [r13+0]
0x140012db4  xor     r8d, r8d
0x140012db7  mov     [rbp+4Fh+var_88], eax
0x140012dba  lea     rax, [rbp+4Fh+var_68]
0x140012dbe  mov     [rbp+4Fh+var_80], rax
0x140012dc2  mov     rax, [rsi+8]
0x140012dc6  mov     [rbp+4Fh+var_70], rax
0x140012dca  movzx   eax, word ptr [rsi]
0x140012dcd  mov     [rbp+4Fh+var_68], eax
0x140012dd0  lea     rax, [rsp+120h+var_E0]
0x140012dd5  mov     [rbp+4Fh+var_60], rax
0x140012dd9  lea     rax, [rsp+120h+Handle]
0x140012dde  mov     [rbp+4Fh+var_50], rax
0x140012de2  lea     rax, [rbp+4Fh+var_C0]
0x140012de6  mov     [rsp+120h+var_F8], rax
0x140012deb  mov     [rsp+120h+var_100], 8
0x140012df3  mov     [rbp+4Fh+var_84], 0
0x140012dfa  mov     [rbp+4Fh+var_78], 2
0x140012e02  mov     [rbp+4Fh+var_64], 0
0x140012e09  mov     [rsp+120h+var_E0], r12d
0x140012e0e  mov     [rbp+4Fh+var_58], 4
0x140012e16  mov     dword ptr [rsp+120h+Handle], ebx
0x140012e1a  mov     [rbp+4Fh+var_48], 4
0x140012e22  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012e27  mov     eax, ebx
0x140012e29  mov     rcx, [rbp+4Fh+var_40]
0x140012e2d  xor     rcx, rsp; StackCookie
0x140012e30  call    __security_check_cookie
0x140012e35  mov     rbx, [rsp+120h+arg_10]
0x140012e3d  add     rsp, 0F0h
0x140012e44  pop     r15
0x140012e46  pop     r14
0x140012e48  pop     r13
0x140012e4a  pop     r12
0x140012e4c  pop     rdi
0x140012e4d  pop     rsi
0x140012e4e  pop     rbp
0x140012e4f  retn
```
