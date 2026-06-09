# COffscreenDC::Realloc(long,long)

- ea: `0x180176014`
- end: `0x18017605c`
- name: `?Realloc@COffscreenDC@@QEAAHJJ@Z`
- size: `72`
- prototype: `__int64 __fastcall(COffscreenDC *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800fdfa8`

## callees

- `0x180176014`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180176038`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180176038`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180176024`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180176024`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180176042`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180176042`

## pseudocode

```c
__int64 __fastcall COffscreenDC::Realloc(COffscreenDC *this, int a2, int a3)
{
  __int64 result; // rax
  __int64 v5; // rdi

  result = (__int64)CreateCompatibleBitmap(*(HDC *)this, a2, a3);
  v5 = result;
  if ( result )
  {
    SelectObject(*(HDC *)this, (HGDIOBJ)result);
    DeleteObject(*((HGDIOBJ *)this + 2));
    result = 1;
    *((_QWORD *)this + 2) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x180176014  mov     [rsp+arg_0], rbx
0x180176019  push    rdi
0x18017601a  sub     rsp, 20h
0x18017601e  mov     rbx, rcx
0x180176021  mov     rcx, [rcx]; hdc
0x180176024  call    cs:__imp_CreateCompatibleBitmap
0x18017602a  mov     rdi, rax
0x18017602d  test    rax, rax
0x180176030  jz      short loc_180176051
0x180176032  mov     rcx, [rbx]; hdc
0x180176035  mov     rdx, rdi; h
0x180176038  call    cs:__imp_SelectObject
0x18017603e  mov     rcx, [rbx+10h]; ho
0x180176042  call    cs:__imp_DeleteObject
0x180176048  mov     eax, 1
0x18017604d  mov     [rbx+10h], rdi
0x180176051  mov     rbx, [rsp+28h+arg_0]
0x180176056  add     rsp, 20h
0x18017605a  pop     rdi
0x18017605b  retn
```
