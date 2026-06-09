# DismMountClass::Unmount(bool)

- ea: `0x180041a20`
- end: `0x180041b17`
- name: `?Unmount@DismMountClass@@QEAAJ_N@Z`
- size: `247`
- prototype: `__int64 __fastcall(DismMountClass *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180042b6c`

## callees

- `0x1800059fc`
- `0x18001ee18`
- `0x180041a20`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180041ac7`
- `KERNEL32!RemoveDirectoryW` at `0x180041ac7`
- `DismApi!DismUnmountImage` at `0x180041a8f`
- `DismApi!DismUnmountImage` at `0x180041a8f`

## string_xrefs

- `0x180041a54`: `commit`
- `0x180041a62`: `DismMountClass::Unmount Dismounting %ls %ls change`
- `0x180041a9e`: `DismMountClass::Unmount DismUnmountImage error 0x%x`
- `0x180041adc`: `DismMountClass::Unmount RemoveDirectoryW error %ls`
- `0x180041aef`: `DismMountClass::Unmount No wim mounted`

## pseudocode

```c
__int64 __fastcall DismMountClass::Unmount(DismMountClass *this, unsigned __int8 a2)
{
  int v3; // edi
  _QWORD *v4; // rsi
  _QWORD *v5; // rax
  const wchar_t *v6; // r9
  char v7; // dl
  _QWORD *v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  const WCHAR *v11; // rax
  _QWORD *v12; // rax

  v3 = a2;
  if ( *((_BYTE *)this + 41) )
  {
    v4 = (_QWORD *)((char *)this + 8);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((_QWORD *)this + 1);
    v6 = L"commit";
    if ( !v7 )
      v6 = L"discard";
    UnattendLogW(0, L"DismMountClass::Unmount Dismounting %ls %ls change", v5, v6);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
    v9 = DismUnmountImage(v8, v3 ^ 1u, 0, 0, 0);
    v10 = v9;
    if ( v9 >= 0 )
      *((_BYTE *)this + 41) = 0;
    else
      UnattendLogW(1, L"DismMountClass::Unmount DismUnmountImage error 0x%x", (unsigned int)v9);
    if ( *((_QWORD *)this + 3) )
    {
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
      if ( !RemoveDirectoryW(v11) )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
        UnattendLogW(2, L"DismMountClass::Unmount RemoveDirectoryW error %ls", v12);
      }
    }
  }
  else
  {
    UnattendLogW(2, L"DismMountClass::Unmount No wim mounted");
    return 1;
  }
  return v10;
}

```

## disassembly

```asm
0x180041a20  mov     [rsp+arg_0], rbx
0x180041a25  mov     [rsp+arg_8], rsi
0x180041a2a  push    rdi
0x180041a2b  sub     rsp, 30h
0x180041a2f  cmp     byte ptr [rcx+29h], 0
0x180041a33  mov     rbx, rcx
0x180041a36  movzx   edi, dl
0x180041a39  jz      loc_180041AEF
0x180041a3f  lea     rsi, [rcx+8]
0x180041a43  mov     rcx, rsi
0x180041a46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041a4b  test    dl, dl
0x180041a4d  lea     rcx, aDiscard; "discard"
0x180041a54  lea     r9, aCommit; "commit"
0x180041a5b  mov     r8, rax
0x180041a5e  cmovz   r9, rcx
0x180041a62  lea     rdx, aDismmountclass_9; "DismMountClass::Unmount Dismounting %ls"...
0x180041a69  xor     ecx, ecx
0x180041a6b  call    UnattendLogW
0x180041a70  mov     rcx, rsi
0x180041a73  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041a78  mov     edx, edi
0x180041a7a  mov     [rsp+38h+var_18], 0
0x180041a83  xor     edx, 1
0x180041a86  xor     r9d, r9d
0x180041a89  xor     r8d, r8d
0x180041a8c  mov     rcx, rax
0x180041a8f  call    cs:__imp_DismUnmountImage
0x180041a95  mov     edi, eax
0x180041a97  test    eax, eax
0x180041a99  jns     short loc_180041AB1
0x180041a9b  mov     r8d, eax
0x180041a9e  lea     rdx, aDismmountclass_14; "DismMountClass::Unmount DismUnmountImag"...
0x180041aa5  mov     ecx, 1
0x180041aaa  call    UnattendLogW
0x180041aaf  jmp     short loc_180041AB5
0x180041ab1  mov     byte ptr [rbx+29h], 0
0x180041ab5  cmp     qword ptr [rbx+18h], 0
0x180041aba  jz      short loc_180041B05
0x180041abc  mov     rcx, rsi
0x180041abf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041ac4  mov     rcx, rax; lpPathName
0x180041ac7  call    cs:__imp_RemoveDirectoryW
0x180041acd  test    eax, eax
0x180041acf  jnz     short loc_180041B05
0x180041ad1  mov     rcx, rsi
0x180041ad4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041ad9  mov     r8, rax
0x180041adc  lea     rdx, aDismmountclass_11; "DismMountClass::Unmount RemoveDirectory"...
0x180041ae3  mov     ecx, 2
0x180041ae8  call    UnattendLogW
0x180041aed  jmp     short loc_180041B05
0x180041aef  lea     rdx, aDismmountclass_4; "DismMountClass::Unmount No wim mounted"
0x180041af6  mov     ecx, 2
0x180041afb  call    UnattendLogW
0x180041b00  mov     edi, 1
0x180041b05  mov     rbx, [rsp+38h+arg_0]
0x180041b0a  mov     eax, edi
0x180041b0c  mov     rsi, [rsp+38h+arg_8]
0x180041b11  add     rsp, 30h
0x180041b15  pop     rdi
0x180041b16  retn
```
