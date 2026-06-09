# WinSAT::StorageDevice::Close(void)

- ea: `0x140060888`
- end: `0x1400608ee`
- name: `?Close@StorageDevice@WinSAT@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(WinSAT::StorageDevice *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14006046c`
- `0x1400605cc`
- `0x14006099c`
- `0x140061378`
- `0x140061494`
- `0x140061600`
- `0x140062a38`
- `0x140065760`
- `0x14006bb04`
- `0x14006c0c8`
- `0x14006c494`
- `0x14006c890`
- `0x14006d680`

## callees

- `0x140016588`
- `0x140060888`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400608bb`
- `KERNEL32!DeleteFileW` at `0x1400608bb`
- `KERNEL32!CloseHandle` at `0x14006089f`
- `KERNEL32!CloseHandle` at `0x14006089f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WinSAT::StorageDevice::Close(WinSAT::StorageDevice *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 9) = -1;
  }
  if ( *((_BYTE *)this + 112) )
    DeleteFileW(*(LPCWSTR *)(*((_QWORD *)this + 4) + 24LL));
  *((_BYTE *)this + 112) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)this + 32);
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 46) = 0;
}

```

## disassembly

```asm
0x140060888  mov     [rsp+arg_0], rbx
0x14006088d  push    rdi
0x14006088e  sub     rsp, 20h
0x140060892  mov     rbx, rcx
0x140060895  mov     rcx, [rcx+48h]; hObject
0x140060899  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006089d  jz      short loc_1400608AD
0x14006089f  call    cs:__imp_CloseHandle
0x1400608a5  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1400608ad  cmp     byte ptr [rbx+70h], 0
0x1400608b1  jz      short loc_1400608C1
0x1400608b3  mov     rcx, [rbx+20h]
0x1400608b7  mov     rcx, [rcx+18h]; lpFileName
0x1400608bb  call    cs:__imp_DeleteFileW
0x1400608c1  lea     rcx, [rbx+20h]
0x1400608c5  mov     byte ptr [rbx+70h], 0
0x1400608c9  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x1400608ce  mov     dword ptr [rbx+58h], 0
0x1400608d5  mov     qword ptr [rbx+28h], 0
0x1400608dd  mov     word ptr [rbx+5Ch], 0
0x1400608e3  mov     rbx, [rsp+28h+arg_0]
0x1400608e8  add     rsp, 20h
0x1400608ec  pop     rdi
0x1400608ed  retn
```
