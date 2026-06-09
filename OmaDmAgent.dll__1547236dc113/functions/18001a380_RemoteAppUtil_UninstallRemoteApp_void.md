# RemoteAppUtil::UninstallRemoteApp(void *)

- ea: `0x18001a380`
- end: `0x18001a3cf`
- name: `?UninstallRemoteApp@RemoteAppUtil@@SAKPEAX@Z`
- size: `79`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000702c`
- `0x18001a098`

## pseudocode

```c
__int64 __fastcall RemoteAppUtil::UninstallRemoteApp(char *a1)
{
  OLECHAR *v2; // rbx
  OLECHAR *v3; // rax
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v6[40]; // [rsp+40h] [rbp-28h] BYREF

  v2 = (OLECHAR *)std::wstring::wstring(&v5, a1);
  v3 = (OLECHAR *)std::wstring::wstring(v6, a1 + 32);
  return RemoteAppUtil::UninstallRemoteApp(v3, v2);
}

```

## disassembly

```asm
0x18001a380  mov     r11, rsp
0x18001a383  mov     [r11+18h], rbx
0x18001a387  push    rdi
0x18001a388  sub     rsp, 60h
0x18001a38c  mov     rdi, rcx
0x18001a38f  lea     rax, [r11-48h]
0x18001a393  mov     [r11+8], rax
0x18001a397  mov     rdx, rcx
0x18001a39a  lea     rcx, [r11-48h]
0x18001a39e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a3a3  mov     rbx, rax
0x18001a3a6  lea     rdx, [rdi+20h]
0x18001a3aa  lea     rcx, [rsp+68h+var_28]
0x18001a3af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a3b4  nop
0x18001a3b5  mov     rdx, rbx; OLECHAR *
0x18001a3b8  mov     rcx, rax; psz
0x18001a3bb  call    ?UninstallRemoteApp@RemoteAppUtil@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RemoteAppUtil::UninstallRemoteApp(std::wstring,std::wstring)
0x18001a3c0  mov     rbx, [rsp+68h+arg_10]
0x18001a3c8  add     rsp, 60h
0x18001a3cc  pop     rdi
0x18001a3cd  retn
```
