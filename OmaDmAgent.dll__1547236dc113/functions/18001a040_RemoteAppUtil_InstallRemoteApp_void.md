# RemoteAppUtil::InstallRemoteApp(void *)

- ea: `0x18001a040`
- end: `0x18001a08f`
- name: `?InstallRemoteApp@RemoteAppUtil@@SAKPEAX@Z`
- size: `79`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000702c`
- `0x180019d2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteAppUtil::InstallRemoteApp(char *a1)
{
  OLECHAR *v2; // rbx
  OLECHAR *v3; // rax
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v6[40]; // [rsp+40h] [rbp-28h] BYREF

  v2 = (OLECHAR *)std::wstring::wstring(&v5, a1);
  v3 = (OLECHAR *)std::wstring::wstring(v6, a1 + 32);
  return RemoteAppUtil::InstallRemoteApp(v3, v2);
}

```

## disassembly

```asm
0x18001a040  mov     r11, rsp
0x18001a043  mov     [r11+18h], rbx
0x18001a047  push    rdi
0x18001a048  sub     rsp, 60h
0x18001a04c  mov     rdi, rcx
0x18001a04f  lea     rax, [r11-48h]
0x18001a053  mov     [r11+8], rax
0x18001a057  mov     rdx, rcx
0x18001a05a  lea     rcx, [r11-48h]
0x18001a05e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a063  mov     rbx, rax
0x18001a066  lea     rdx, [rdi+20h]
0x18001a06a  lea     rcx, [rsp+68h+var_28]
0x18001a06f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a074  nop
0x18001a075  mov     rdx, rbx; OLECHAR *
0x18001a078  mov     rcx, rax; psz
0x18001a07b  call    ?InstallRemoteApp@RemoteAppUtil@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RemoteAppUtil::InstallRemoteApp(std::wstring,std::wstring)
0x18001a080  mov     rbx, [rsp+68h+arg_10]
0x18001a088  add     rsp, 60h
0x18001a08c  pop     rdi
0x18001a08d  retn
```
