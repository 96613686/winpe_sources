# std::unique_ptr<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>,std::default_delete<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>>>::_Delete(void)

- ea: `0x1800072d8`
- end: `0x180007324`
- name: `?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ`
- size: `76`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x180006af8`
- `0x18000d7d0`
- `0x18000e0d8`
- `0x18000e90c`

## callees

- `0x1800072d8`
- `0x1800080d4`
- `0x18000ea94`

## pseudocode

```c
void __fastcall std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(_QWORD **a1)
{
  _QWORD *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
    {
      std::vector<NetSetup2::Property>::_Destroy(a1, *v1, v1[1]);
      operator delete((void *)*v1);
      *v1 = 0;
      v1[1] = 0;
      v1[2] = 0;
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800072d8  push    rbx
0x1800072da  sub     rsp, 20h
0x1800072de  mov     rbx, [rcx]
0x1800072e1  test    rbx, rbx
0x1800072e4  jz      short loc_18000731E
0x1800072e6  mov     rdx, [rbx]
0x1800072e9  test    rdx, rdx
0x1800072ec  jz      short loc_180007316
0x1800072ee  mov     r8, [rbx+8]
0x1800072f2  call    ?_Destroy@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAXPEAVProperty@NetSetup2@@0@Z; std::vector<NetSetup2::Property>::_Destroy(NetSetup2::Property *,NetSetup2::Property *)
0x1800072f7  mov     rcx, [rbx]; Block
0x1800072fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072ff  mov     qword ptr [rbx], 0
0x180007306  mov     qword ptr [rbx+8], 0
0x18000730e  mov     qword ptr [rbx+10h], 0
0x180007316  mov     rcx, rbx; Block
0x180007319  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000731e  add     rsp, 20h
0x180007322  pop     rbx
0x180007323  retn
```
