# Windows::Internal::DialogBlocking::Consts::ShutdownEventName(ulong)

- ea: `0x18000ab20`
- end: `0x18000ab8a`
- name: `?ShutdownEventName@Consts@DialogBlocking@Internal@Windows@@SA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@K@Z`
- size: `106`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008da8`

## callees

- `0x180008ec8`
- `0x180009568`
- `0x18000ab20`

## string_xrefs

- `0x18000ab78`: `base\embedded\sys\dialogblocking\common\lib\constants.cpp`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::DialogBlocking::Consts::ShutdownEventName(_QWORD *a1, unsigned int a2)
{
  int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         (__int64)a1,
         L"Global\\Microsoft-Windows-Embedded-DialogBlocking-Shutdown-%u",
         a2);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB,
      (int)"base\\embedded\\sys\\dialogblocking\\common\\lib\\constants.cpp",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18000ab20  mov     [rsp+arg_0], rcx
0x18000ab25  push    rbx
0x18000ab26  sub     rsp, 30h
0x18000ab2a  mov     rbx, rcx
0x18000ab2d  mov     [rsp+38h+var_18], 0
0x18000ab35  mov     qword ptr [rcx], 0
0x18000ab3c  mov     qword ptr [rcx+8], 0
0x18000ab44  mov     qword ptr [rcx+10h], 0
0x18000ab4c  mov     [rsp+38h+var_18], 1; int
0x18000ab54  mov     r8d, edx
0x18000ab57  lea     rdx, aGlobalMicrosof; "Global\\Microsoft-Windows-Embedded-Dial"...
0x18000ab5e  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000ab63  test    eax, eax
0x18000ab65  js      short loc_18000AB70
0x18000ab67  mov     rax, rbx
0x18000ab6a  add     rsp, 30h
0x18000ab6e  pop     rbx
0x18000ab6f  retn
0x18000ab70  mov     rcx, [rsp+38h]; this
0x18000ab75  mov     r9d, eax; char *
0x18000ab78  lea     r8, aBaseEmbeddedSy_1; "base\\embedded\\sys\\dialogblocking\\co"...
0x18000ab7f  mov     edx, 0Bh; void *
0x18000ab84  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
