# ipx::mtf::CFuzzyTable::RemoveAllEntries(void)

- ea: `0x18000ff34`
- end: `0x18000ffc9`
- name: `?RemoveAllEntries@CFuzzyTable@mtf@ipx@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(ipx::mtf::CFuzzyTable *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e6e0`
- `0x18000ee80`
- `0x18000f570`

## callees

- `0x18000ff34`

## import_xrefs

- `msvcrt!free` at `0x18000ff88`
- `msvcrt!free` at `0x18000ffa9`
- `msvcrt!free` at `0x18000ff88`
- `msvcrt!free` at `0x18000ffa9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ff69`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ff69`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ff5c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ff5c`

## pseudocode

```c
void __fastcall ipx::mtf::CFuzzyTable::RemoveAllEntries(ipx::mtf::CFuzzyTable *this)
{
  __int64 v1; // rsi
  void **i; // rbx
  OLECHAR *v4; // r14
  void *v5; // rcx

  v1 = 0;
  for ( i = (void **)((char *)this + 24); (unsigned int)v1 < *((_DWORD *)this + 2); v1 = (unsigned int)(v1 + 1) )
  {
    v4 = (OLECHAR *)*((_QWORD *)*i + 3 * v1 + 1);
    if ( SysStringLen(v4) )
    {
      SysFreeString(v4);
      *((_QWORD *)*i + 3 * v1 + 1) = 0;
    }
    v5 = (void *)*((_QWORD *)*i + 3 * v1 + 2);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)*i + 3 * v1 + 2) = 0;
    }
  }
  if ( *i )
  {
    free(*i);
    *i = 0;
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000ff34  push    rbx
0x18000ff36  push    rbp
0x18000ff37  push    rsi
0x18000ff38  push    rdi
0x18000ff39  push    r14
0x18000ff3b  sub     rsp, 20h
0x18000ff3f  xor     esi, esi
0x18000ff41  lea     rbx, [rcx+18h]
0x18000ff45  mov     rdi, rcx
0x18000ff48  cmp     [rcx+8], esi
0x18000ff4b  jbe     short loc_18000FFA1
0x18000ff4d  mov     rax, [rbx]
0x18000ff50  lea     rbp, [rsi+rsi*2]
0x18000ff54  mov     r14, [rax+rbp*8+8]
0x18000ff59  mov     rcx, r14; pbstr
0x18000ff5c  call    cs:__imp_SysStringLen
0x18000ff62  test    eax, eax
0x18000ff64  jz      short loc_18000FF7B
0x18000ff66  mov     rcx, r14; bstrString
0x18000ff69  call    cs:__imp_SysFreeString
0x18000ff6f  mov     rax, [rbx]
0x18000ff72  mov     qword ptr [rax+rbp*8+8], 0
0x18000ff7b  mov     rax, [rbx]
0x18000ff7e  mov     rcx, [rax+rbp*8+10h]; Block
0x18000ff83  test    rcx, rcx
0x18000ff86  jz      short loc_18000FF9A
0x18000ff88  call    cs:__imp_free
0x18000ff8e  mov     rax, [rbx]
0x18000ff91  mov     qword ptr [rax+rbp*8+10h], 0
0x18000ff9a  inc     esi
0x18000ff9c  cmp     esi, [rdi+8]
0x18000ff9f  jb      short loc_18000FF4D
0x18000ffa1  mov     rcx, [rbx]; Block
0x18000ffa4  test    rcx, rcx
0x18000ffa7  jz      short loc_18000FFB6
0x18000ffa9  call    cs:__imp_free
0x18000ffaf  mov     qword ptr [rbx], 0
0x18000ffb6  mov     qword ptr [rdi+8], 0
0x18000ffbe  add     rsp, 20h
0x18000ffc2  pop     r14
0x18000ffc4  pop     rdi
0x18000ffc5  pop     rsi
0x18000ffc6  pop     rbp
0x18000ffc7  pop     rbx
0x18000ffc8  retn
```
