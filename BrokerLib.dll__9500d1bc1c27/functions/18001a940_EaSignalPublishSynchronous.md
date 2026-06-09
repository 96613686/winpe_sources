# EaSignalPublishSynchronous

- ea: `0x18001a940`
- end: `0x18001aaa4`
- name: `EaSignalPublishSynchronous`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800128fc`

## callees

- `0x180015af0`
- `0x18001a940`
- `0x18001ae60`

## import_xrefs

- `ntdll!RtlWaitForWnfMetaNotification` at `0x18001aa1a`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x18001aa1a`
- `ntdll!NtQueryWnfStateData` at `0x18001a9ea`
- `ntdll!NtQueryWnfStateData` at `0x18001a9ea`
- `ntdll!NtUpdateWnfStateData` at `0x18001aa69`
- `ntdll!NtUpdateWnfStateData` at `0x18001aa69`

## pseudocode

```c
__int64 __fastcall EaSignalPublishSynchronous(_QWORD *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rdi
  int v10; // [rsp+40h] [rbp-1058h] BYREF
  int v11; // [rsp+44h] [rbp-1054h]
  int v12; // [rsp+48h] [rbp-1050h] BYREF
  _BYTE v13[4096]; // [rsp+50h] [rbp-1048h] BYREF

  v12 = 0;
  v11 = 0;
  v10 = 0;
  if ( a4 == -1 )
    v7 = -1;
  else
    v7 = ((((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64)
       + a4;
  while ( 1 )
  {
    v10 = 4096;
    result = NtQueryWnfStateData(a1, 0, 0, &v12, v13, &v10);
    if ( (int)result < 0 )
      break;
    result = RtlWaitForWnfMetaNotification(*a1, 8);
    if ( (int)result < 0 )
      break;
    v9 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    if ( v11 == 8 )
    {
      result = NtUpdateWnfStateData(a1, a2, a3, 0, 0, v12, 1);
      if ( (int)result > -1 )
        break;
    }
    if ( v9 >= v7 )
      return 3221226621LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001a940  push    rbx
0x18001a942  push    rbp
0x18001a943  push    rsi
0x18001a944  push    rdi
0x18001a945  push    r12
0x18001a947  push    r13
0x18001a949  push    r14
0x18001a94b  mov     eax, 1060h
0x18001a950  call    _alloca_probe
0x18001a955  sub     rsp, rax
0x18001a958  mov     rax, cs:__security_cookie
0x18001a95f  xor     rax, rsp
0x18001a962  mov     [rsp+1098h+var_48], rax
0x18001a96a  mov     rbp, rdx
0x18001a96d  mov     [rsp+1098h+var_1050], 0
0x18001a975  mov     [rsp+1098h+var_1054], 0
0x18001a97d  mov     r13d, 7FFE0320h
0x18001a983  mov     [rsp+1098h+var_1058], 0
0x18001a98b  mov     r12d, 0FFFFFFFFh
0x18001a991  mov     edx, ds:7FFE0004h
0x18001a998  mov     r14d, r8d
0x18001a99b  shl     rdx, 20h
0x18001a99f  mov     rsi, rcx
0x18001a9a2  mov     rax, [r13+0]
0x18001a9a6  shl     rax, 8
0x18001a9aa  mul     rdx
0x18001a9ad  mov     rdi, rdx
0x18001a9b0  cmp     r9d, r12d
0x18001a9b3  jnz     short loc_18001A9BB
0x18001a9b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a9b9  jmp     short loc_18001A9C1
0x18001a9bb  mov     ebx, r9d
0x18001a9be  add     rbx, rdx
0x18001a9c1  lea     rax, [rsp+1098h+var_1058]
0x18001a9c6  mov     [rsp+1098h+var_1058], 1000h
0x18001a9ce  mov     [rsp+1098h+var_1070], rax
0x18001a9d3  lea     r9, [rsp+1098h+var_1050]
0x18001a9d8  lea     rax, [rsp+1098h+var_1048]
0x18001a9dd  xor     r8d, r8d
0x18001a9e0  xor     edx, edx
0x18001a9e2  mov     [rsp+1098h+var_1078], rax
0x18001a9e7  mov     rcx, rsi
0x18001a9ea  call    cs:__imp_NtQueryWnfStateData
0x18001a9f0  test    eax, eax
0x18001a9f2  js      loc_18001AA82
0x18001a9f8  mov     r8, rbx
0x18001a9fb  sub     r8, rdi
0x18001a9fe  cmp     r8, r12
0x18001aa01  jbe     short loc_18001AA06
0x18001aa03  mov     r8d, r12d
0x18001aa06  mov     rcx, [rsi]
0x18001aa09  lea     rax, [rsp+1098h+var_1054]
0x18001aa0e  xor     r9d, r9d
0x18001aa11  mov     [rsp+1098h+var_1078], rax
0x18001aa16  lea     edx, [r9+8]
0x18001aa1a  call    cs:__imp_RtlWaitForWnfMetaNotification
0x18001aa20  test    eax, eax
0x18001aa22  js      short loc_18001AA82
0x18001aa24  mov     rax, [r13+0]
0x18001aa28  mov     ecx, ds:7FFE0004h
0x18001aa2f  shl     rax, 8
0x18001aa33  shl     rcx, 20h
0x18001aa37  mul     rcx
0x18001aa3a  cmp     [rsp+1098h+var_1054], 8
0x18001aa3f  mov     rdi, rdx
0x18001aa42  jnz     short loc_18001AA74
0x18001aa44  mov     eax, [rsp+1098h+var_1050]
0x18001aa48  xor     r9d, r9d
0x18001aa4b  mov     [rsp+1098h+var_1068], 1
0x18001aa53  mov     r8d, r14d
0x18001aa56  mov     dword ptr [rsp+1098h+var_1070], eax
0x18001aa5a  mov     rdx, rbp
0x18001aa5d  mov     rcx, rsi
0x18001aa60  mov     [rsp+1098h+var_1078], 0
0x18001aa69  call    cs:__imp_NtUpdateWnfStateData
0x18001aa6f  cmp     eax, 0FFFFFFFFh
0x18001aa72  jg      short loc_18001AA82
0x18001aa74  cmp     rdi, rbx
0x18001aa77  jb      loc_18001A9C1
0x18001aa7d  mov     eax, 0C000047Dh
0x18001aa82  mov     rcx, [rsp+1098h+var_48]
0x18001aa8a  xor     rcx, rsp; StackCookie
0x18001aa8d  call    __security_check_cookie
0x18001aa92  add     rsp, 1060h
0x18001aa99  pop     r14
0x18001aa9b  pop     r13
0x18001aa9d  pop     r12
0x18001aa9f  pop     rdi
0x18001aaa0  pop     rsi
0x18001aaa1  pop     rbp
0x18001aaa2  pop     rbx
0x18001aaa3  retn
```
