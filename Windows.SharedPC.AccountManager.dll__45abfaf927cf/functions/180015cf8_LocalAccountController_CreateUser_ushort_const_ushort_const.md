# LocalAccountController::CreateUser(ushort const *,ushort const *)

- ea: `0x180015cf8`
- end: `0x180015da1`
- name: `?CreateUser@LocalAccountController@@AEAAXPEBG0@Z`
- size: `169`
- prototype: `void __fastcall(LocalAccountController *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015b40`

## callees

- `0x180003fc0`
- `0x180015cf8`
- `0x1800198d4`
- `0x1800237f0`

## import_xrefs

- `samcli!NetUserAdd` at `0x180015d62`
- `samcli!NetUserAdd` at `0x180015d62`

## string_xrefs

- `0x180015d7b`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocalAccountController::CreateUser(
        LocalAccountController *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  DWORD v5; // eax
  int v6; // eax
  BYTE buf[8]; // [rsp+20h] [rbp-A8h] BYREF
  const WCHAR *v8; // [rsp+28h] [rbp-A0h]
  int v9; // [rsp+34h] [rbp-94h]
  int v10; // [rsp+48h] [rbp-80h]
  const unsigned __int16 *v11; // [rsp+60h] [rbp-68h]
  int v12; // [rsp+88h] [rbp-40h]
  int v13; // [rsp+8Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  memset_0(buf, 0, 0x98u);
  *(_QWORD *)buf = a2;
  v8 = &String2;
  v11 = a3;
  v9 = 1;
  v10 = 66081;
  v12 = -1;
  v13 = -1;
  v5 = NetUserAdd(0, 2u, buf, 0);
  v6 = NetpApiStatusToNtStatus(v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xF0,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v6,
      *(int *)buf);
}

```

## disassembly

```asm
0x180015cf8  mov     [rsp+arg_0], rbx
0x180015cfd  push    rdi
0x180015cfe  sub     rsp, 0C0h
0x180015d05  mov     rdi, r8
0x180015d08  lea     rcx, [rsp+0C8h+buf]; void *
0x180015d0d  mov     rbx, rdx
0x180015d10  mov     r8d, 98h; Size
0x180015d16  xor     edx, edx; Val
0x180015d18  call    memset_0
0x180015d1d  lea     rax, String2
0x180015d24  mov     qword ptr [rsp+0C8h+buf], rbx; int
0x180015d29  xor     r9d, r9d; parm_err
0x180015d2c  mov     [rsp+0C8h+var_A0], rax
0x180015d31  or      eax, 0FFFFFFFFh
0x180015d34  mov     [rsp+0C8h+var_68], rdi
0x180015d39  lea     r8, [rsp+0C8h+buf]; buf
0x180015d3e  mov     [rsp+0C8h+var_94], 1
0x180015d46  xor     ecx, ecx; servername
0x180015d48  mov     [rsp+0C8h+var_80], 10221h
0x180015d50  lea     edx, [r9+2]; level
0x180015d54  mov     [rsp+0C8h+var_40], eax
0x180015d5b  mov     [rsp+0C8h+var_3C], eax
0x180015d62  call    cs:__imp_NetUserAdd
0x180015d68  mov     ecx, eax
0x180015d6a  call    NetpApiStatusToNtStatus
0x180015d6f  test    eax, eax
0x180015d71  jns     short loc_180015D90
0x180015d73  mov     rcx, [rsp+0C8h]; this
0x180015d7b  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015d82  mov     r9d, eax; char *
0x180015d85  mov     edx, 0F0h; void *
0x180015d8a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015d90  mov     rbx, [rsp+0C8h+arg_0]
0x180015d98  add     rsp, 0C0h
0x180015d9f  pop     rdi
0x180015da0  retn
```
