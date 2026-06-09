# DavRemoveDummyShareFromFileName

- ea: `0x1800043f0`
- end: `0x1800044b4`
- name: `DavRemoveDummyShareFromFileName`
- size: `196`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800043f0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180004426`
- `msvcrt!_wcsnicmp` at `0x180004426`
- `msvcrt!wcschr` at `0x180004445`
- `msvcrt!wcschr` at `0x18000449a`
- `msvcrt!wcschr` at `0x180004445`
- `msvcrt!wcschr` at `0x18000449a`

## pseudocode

```c
__int64 __fastcall DavRemoveDummyShareFromFileName(wchar_t *Str)
{
  wchar_t *v1; // rbx
  __int64 result; // rax
  wchar_t *v3; // rax
  __int64 v4; // r9

  v1 = Str;
  if ( Str )
  {
    while ( *v1 )
    {
      if ( !_wcsnicmp(v1, L"DavWWWRoot", 0xAu) )
      {
        if ( !*v1 )
          return 0;
        v3 = wcschr(v1, 0x2Fu);
        if ( v3 || (v3 = wcschr(v1, 0x5Cu)) != 0 )
        {
          v4 = 0;
          if ( v3[1] )
          {
            do
            {
              v1[v4] = v3[v4 + 1];
              v3[v4 + 1] = 0;
              v4 = (unsigned int)(v4 + 1);
            }
            while ( v3[v4 + 1] );
          }
          result = 11;
          v1[v4] = 0;
        }
        else
        {
          result = 10;
          *v1 = 0;
        }
        return result;
      }
      if ( !++v1 )
        return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800043f0  mov     [rsp+arg_0], rbx
0x1800043f5  push    rdi
0x1800043f6  sub     rsp, 20h
0x1800043fa  xor     edi, edi
0x1800043fc  mov     rbx, rcx
0x1800043ff  test    rcx, rcx
0x180004402  jnz     short loc_180004411
0x180004404  mov     eax, edi
0x180004406  mov     rbx, [rsp+28h+arg_0]
0x18000440b  add     rsp, 20h
0x18000440f  pop     rdi
0x180004410  retn
0x180004411  cmp     [rbx], di
0x180004414  jz      short loc_180004404
0x180004416  mov     r8d, 0Ah; MaxCount
0x18000441c  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x180004423  mov     rcx, rbx; String1
0x180004426  call    cs:__imp__wcsnicmp
0x18000442c  test    eax, eax
0x18000442e  jz      short loc_180004438
0x180004430  add     rbx, 2
0x180004434  jz      short loc_180004404
0x180004436  jmp     short loc_180004411
0x180004438  cmp     [rbx], di
0x18000443b  jz      short loc_180004404
0x18000443d  mov     edx, 2Fh ; '/'; Ch
0x180004442  mov     rcx, rbx; Str
0x180004445  call    cs:__imp_wcschr
0x18000444b  test    rax, rax
0x18000444e  jz      short loc_180004492
0x180004450  xor     r9d, r9d
0x180004453  mov     r8d, 0Bh
0x180004459  cmp     [rax+2], di
0x18000445d  jz      short loc_18000447D
0x18000445f  movzx   ecx, word ptr [rax+r9*2+2]
0x180004465  mov     [rbx+r9*2], cx
0x18000446a  xor     ecx, ecx
0x18000446c  mov     [rax+r9*2+2], cx
0x180004472  inc     r9d
0x180004475  cmp     [rax+r9*2+2], cx
0x18000447b  jnz     short loc_18000445F
0x18000447d  xor     ecx, ecx
0x18000447f  mov     eax, r8d
0x180004482  mov     [rbx+r9*2], cx
0x180004487  mov     rbx, [rsp+28h+arg_0]
0x18000448c  add     rsp, 20h
0x180004490  pop     rdi
0x180004491  retn
0x180004492  mov     edx, 5Ch ; '\'; Ch
0x180004497  mov     rcx, rbx; Str
0x18000449a  call    cs:__imp_wcschr
0x1800044a0  test    rax, rax
0x1800044a3  jnz     short loc_180004450
0x1800044a5  xor     ecx, ecx
0x1800044a7  mov     eax, 0Ah
0x1800044ac  mov     [rbx], cx
0x1800044af  jmp     loc_180004406
```
