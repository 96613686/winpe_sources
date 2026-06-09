# CHString::CopyBeforeWrite(void)

- ea: `0x140010b40`
- end: `0x140010bad`
- name: `?CopyBeforeWrite@CHString@@IEAAXXZ`
- size: `109`
- prototype: `void __fastcall(const unsigned __int16 **this)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x140011450`
- `0x140011480`
- `0x1400114b0`
- `0x140011670`
- `0x1400117d0`
- `0x140011910`
- `0x1400119a0`

## callees

- `0x1400027e1`
- `0x140010630`
- `0x140010b40`
- `0x1400115e0`

## pseudocode

```c
void __fastcall CHString::CopyBeforeWrite(const unsigned __int16 **this)
{
  const unsigned __int16 *v1; // rdx
  char *v2; // rbx
  int *v4; // rax

  v1 = *this;
  v2 = byte_140024890;
  v4 = (int *)byte_140024890;
  if ( *this != afxPchNil )
    v4 = (int *)(v1 - 6);
  if ( *v4 > 1 )
  {
    if ( v1 != afxPchNil )
      v2 = (char *)(v1 - 6);
    CHString::Release((CHString *)this);
    CHString::AllocBuffer((CHString *)this, *((_DWORD *)v2 + 1));
    memcpy_0((void *)*this, v2 + 12, 2LL * (*((_DWORD *)v2 + 1) + 1));
  }
}

```

## disassembly

```asm
0x140010b40  mov     [rsp+arg_0], rbx
0x140010b45  push    rdi
0x140010b46  sub     rsp, 20h
0x140010b4a  mov     rdx, [rcx]
0x140010b4d  lea     rbx, byte_140024890
0x140010b54  mov     rdi, rcx
0x140010b57  mov     rax, rbx
0x140010b5a  mov     rcx, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140010b61  cmp     rdx, rcx
0x140010b64  lea     r8, [rdx-0Ch]
0x140010b68  cmovnz  rax, r8
0x140010b6c  cmp     dword ptr [rax], 1
0x140010b6f  jle     short loc_140010BA2
0x140010b71  cmp     rdx, rcx
0x140010b74  mov     rcx, rdi; this
0x140010b77  cmovnz  rbx, r8
0x140010b7b  call    ?Release@CHString@@QEAAXXZ; CHString::Release(void)
0x140010b80  mov     edx, [rbx+4]; int
0x140010b83  mov     rcx, rdi; this
0x140010b86  call    ?AllocBuffer@CHString@@IEAAXH@Z; CHString::AllocBuffer(int)
0x140010b8b  mov     eax, [rbx+4]
0x140010b8e  lea     rdx, [rbx+0Ch]; Src
0x140010b92  mov     rcx, [rdi]; void *
0x140010b95  inc     eax
0x140010b97  movsxd  r8, eax
0x140010b9a  add     r8, r8; Size
0x140010b9d  call    memcpy_0
0x140010ba2  mov     rbx, [rsp+28h+arg_0]
0x140010ba7  add     rsp, 20h
0x140010bab  pop     rdi
0x140010bac  retn
```
