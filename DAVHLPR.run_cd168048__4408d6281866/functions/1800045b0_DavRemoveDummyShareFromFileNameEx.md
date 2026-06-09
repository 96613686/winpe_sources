# DavRemoveDummyShareFromFileNameEx

- ea: `0x1800045b0`
- end: `0x1800046b5`
- name: `DavRemoveDummyShareFromFileNameEx`
- size: `261`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800045b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800045e9`
- `msvcrt!_wcsnicmp` at `0x1800045e9`
- `msvcrt!wcschr` at `0x18000461c`
- `msvcrt!wcschr` at `0x18000462f`
- `msvcrt!wcschr` at `0x18000461c`
- `msvcrt!wcschr` at `0x18000462f`

## pseudocode

```c
__int64 __fastcall DavRemoveDummyShareFromFileNameEx(wchar_t *Str, int a2)
{
  unsigned int v2; // ebx
  wchar_t *v4; // rdi
  wchar_t *v6; // rax
  wchar_t *v7; // rdx
  wchar_t v8; // ax
  __int64 v9; // r8
  __int64 v10; // rcx

  v2 = 0;
  v4 = Str;
  if ( Str )
  {
    while ( *v4 )
    {
      if ( !_wcsnicmp(v4, L"DavWWWRoot", 0xAu) )
      {
        if ( !*v4 )
          return v2;
        v6 = wcschr(v4, 0x2Fu);
        if ( v6 || (v6 = wcschr(v4, 0x5Cu)) != 0 )
        {
          v7 = v6 + 1;
          v8 = v6[1];
          if ( !v8 && !a2 )
            return 0;
          v9 = 0;
          v2 = 11;
          if ( v8 )
          {
            do
            {
              v10 = v9;
              v9 = (unsigned int)(v9 + 1);
              v4[v10] = v7[v10];
              v7[v10] = 0;
            }
            while ( v7[v9] );
          }
          v4[v9] = 0;
        }
        else if ( a2 )
        {
          v2 = 10;
          *v4 = 0;
        }
        return v2;
      }
      if ( !++v4 )
        return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800045b0  mov     [rsp+arg_0], rbx
0x1800045b5  mov     [rsp+arg_8], rsi
0x1800045ba  push    rdi
0x1800045bb  sub     rsp, 20h
0x1800045bf  xor     ebx, ebx
0x1800045c1  mov     esi, edx
0x1800045c3  mov     rdi, rcx
0x1800045c6  test    rcx, rcx
0x1800045c9  jz      loc_1800046A3
0x1800045cf  nop
0x1800045d0  cmp     [rdi], bx
0x1800045d3  jz      loc_1800046A3
0x1800045d9  mov     r8d, 0Ah; MaxCount
0x1800045df  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x1800045e6  mov     rcx, rdi; String1
0x1800045e9  call    cs:__imp__wcsnicmp
0x1800045ef  test    eax, eax
0x1800045f1  jz      short loc_18000460B
0x1800045f3  add     rdi, 2
0x1800045f7  jnz     short loc_1800045D0
0x1800045f9  mov     eax, ebx
0x1800045fb  mov     rbx, [rsp+28h+arg_0]
0x180004600  mov     rsi, [rsp+28h+arg_8]
0x180004605  add     rsp, 20h
0x180004609  pop     rdi
0x18000460a  retn
0x18000460b  cmp     [rdi], bx
0x18000460e  jz      loc_1800046A3
0x180004614  mov     edx, 2Fh ; '/'; Ch
0x180004619  mov     rcx, rdi; Str
0x18000461c  call    cs:__imp_wcschr
0x180004622  test    rax, rax
0x180004625  jnz     short loc_180004648
0x180004627  mov     edx, 5Ch ; '\'; Ch
0x18000462c  mov     rcx, rdi; Str
0x18000462f  call    cs:__imp_wcschr
0x180004635  test    rax, rax
0x180004638  jnz     short loc_180004648
0x18000463a  test    esi, esi
0x18000463c  jz      short loc_1800046A3
0x18000463e  mov     ebx, 0Ah
0x180004643  mov     [rdi], ax
0x180004646  jmp     short loc_1800046A3
0x180004648  lea     rdx, [rax+2]
0x18000464c  movzx   eax, word ptr [rax+2]
0x180004650  test    ax, ax
0x180004653  jnz     short loc_18000466B
0x180004655  test    esi, esi
0x180004657  jnz     short loc_18000466B
0x180004659  xor     eax, eax
0x18000465b  mov     rbx, [rsp+28h+arg_0]
0x180004660  mov     rsi, [rsp+28h+arg_8]
0x180004665  add     rsp, 20h
0x180004669  pop     rdi
0x18000466a  retn
0x18000466b  xor     r8d, r8d
0x18000466e  mov     ebx, 0Bh
0x180004673  test    ax, ax
0x180004676  jz      short loc_18000469C
0x180004678  nop     dword ptr [rax+rax+00000000h]
0x180004680  lea     rcx, [r8+r8]
0x180004684  inc     r8d
0x180004687  movzx   eax, word ptr [rdx+rcx]
0x18000468b  mov     [rdi+rcx], ax
0x18000468f  xor     eax, eax
0x180004691  mov     [rdx+rcx], ax
0x180004695  cmp     [rdx+r8*2], ax
0x18000469a  jnz     short loc_180004680
0x18000469c  xor     eax, eax
0x18000469e  mov     [rdi+r8*2], ax
0x1800046a3  mov     rsi, [rsp+28h+arg_8]
0x1800046a8  mov     eax, ebx
0x1800046aa  mov     rbx, [rsp+28h+arg_0]
0x1800046af  add     rsp, 20h
0x1800046b3  pop     rdi
0x1800046b4  retn
```
