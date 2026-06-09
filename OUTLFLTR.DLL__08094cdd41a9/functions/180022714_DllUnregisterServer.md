# DllUnregisterServer

- ea: `0x180022714`
- end: `0x1800227d4`
- name: `DllUnregisterServer`
- size: `192`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180022714`
- `0x180022858`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18002272d`
- `KERNEL32!GetThreadLocale` at `0x18002272d`
- `KERNEL32!SetThreadLocale` at `0x18002273a`
- `KERNEL32!SetThreadLocale` at `0x1800227b1`
- `KERNEL32!SetThreadLocale` at `0x18002273a`
- `KERNEL32!SetThreadLocale` at `0x1800227b1`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // ebp
  HRESULT v1; // ebx
  __int64 *v2; // rdi
  unsigned __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !qword_1800A47C8 || (v1 = qword_1800A47C8(), v1 >= 0) )
  {
    v2 = (__int64 *)qword_1800A3740;
    v3 = qword_1800A3748;
    v1 = 0;
    while ( (unsigned __int64)v2 < v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (*(__int64 (**)(void))(v4 + 56))();
        v1 = sub_180022858(*(GUID **)v4, v5, 0);
        if ( v1 < 0 )
          break;
        v1 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 8))(0);
        if ( v1 < 0 )
          break;
        v3 = qword_1800A3748;
      }
      ++v2;
    }
  }
  if ( v1 >= 0 )
    v1 = 0;
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x180022714  mov     rax, rsp
0x180022717  mov     [rax+8], rbx
0x18002271b  mov     [rax+10h], rbp
0x18002271f  mov     [rax+18h], rsi
0x180022723  mov     [rax+20h], rdi
0x180022727  push    r12
0x180022729  sub     rsp, 20h
0x18002272d  call    cs:GetThreadLocale
0x180022733  mov     ecx, 800h; Locale
0x180022738  mov     ebp, eax
0x18002273a  call    cs:SetThreadLocale
0x180022740  mov     r11, cs:qword_1800A47C8
0x180022747  xor     r12d, r12d
0x18002274a  cmp     r11, r12
0x18002274d  jz      short loc_180022759
0x18002274f  call    r11 ; qword_1800A47C8
0x180022752  cmp     eax, r12d
0x180022755  mov     ebx, eax
0x180022757  jl      short loc_1800227A8
0x180022759  mov     rdi, cs:qword_1800A3740
0x180022760  mov     rax, cs:qword_1800A3748
0x180022767  mov     ebx, r12d
0x18002276a  jmp     short loc_1800227A3
0x18002276c  mov     rsi, [rdi]
0x18002276f  cmp     rsi, r12
0x180022772  jz      short loc_18002279F
0x180022774  call    qword ptr [rsi+38h]
0x180022777  mov     rcx, [rsi]; rguid
0x18002277a  xor     r8d, r8d
0x18002277d  mov     rdx, rax
0x180022780  call    sub_180022858
0x180022785  cmp     eax, r12d
0x180022788  mov     ebx, eax
0x18002278a  jl      short loc_1800227A8
0x18002278c  xor     ecx, ecx
0x18002278e  call    qword ptr [rsi+8]
0x180022791  cmp     eax, r12d
0x180022794  mov     ebx, eax
0x180022796  jl      short loc_1800227A8
0x180022798  mov     rax, cs:qword_1800A3748
0x18002279f  add     rdi, 8
0x1800227a3  cmp     rdi, rax
0x1800227a6  jb      short loc_18002276C
0x1800227a8  cmp     ebx, r12d
0x1800227ab  mov     ecx, ebp; Locale
0x1800227ad  cmovge  ebx, r12d
0x1800227b1  call    cs:SetThreadLocale
0x1800227b7  mov     rbp, [rsp+28h+arg_8]
0x1800227bc  mov     rsi, [rsp+28h+arg_10]
0x1800227c1  mov     rdi, [rsp+28h+arg_18]
0x1800227c6  mov     eax, ebx
0x1800227c8  mov     rbx, [rsp+28h+arg_0]
0x1800227cd  add     rsp, 20h
0x1800227d1  pop     r12
0x1800227d3  retn
```
