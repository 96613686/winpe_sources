# DllRegisterServer

- ea: `0x180022660`
- end: `0x180022713`
- name: `DllRegisterServer`
- size: `179`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180022660`
- `0x180022858`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180022674`
- `KERNEL32!GetThreadLocale` at `0x180022674`
- `KERNEL32!SetThreadLocale` at `0x180022681`
- `KERNEL32!SetThreadLocale` at `0x1800226f6`
- `KERNEL32!SetThreadLocale` at `0x180022681`
- `KERNEL32!SetThreadLocale` at `0x1800226f6`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  __int64 *v1; // rdi
  unsigned __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 v4; // rsi
  __int64 v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = (__int64 *)qword_1800A3740;
  v2 = qword_1800A3748;
  v3 = 0;
  while ( (unsigned __int64)v1 < v2 )
  {
    v4 = *v1;
    if ( *v1 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64))(v4 + 8))(1);
      if ( v3 < 0 )
        break;
      v5 = (*(__int64 (**)(void))(v4 + 56))();
      v3 = sub_180022858(*(GUID **)v4, v5, 1);
      if ( v3 < 0 )
        break;
      v2 = qword_1800A3748;
    }
    ++v1;
  }
  if ( v3 >= 0 && qword_1800A47C0 )
    v3 = qword_1800A47C0(hModule);
  SetThreadLocale(ThreadLocale);
  return v3;
}

```

## disassembly

```asm
0x180022660  mov     [rsp+arg_0], rbx
0x180022665  mov     [rsp+arg_8], rbp
0x18002266a  mov     [rsp+arg_10], rsi
0x18002266f  push    rdi
0x180022670  sub     rsp, 20h
0x180022674  call    cs:GetThreadLocale
0x18002267a  mov     ecx, 800h; Locale
0x18002267f  mov     ebp, eax
0x180022681  call    cs:SetThreadLocale
0x180022687  mov     rdi, cs:qword_1800A3740
0x18002268e  mov     rdx, cs:qword_1800A3748
0x180022695  xor     ebx, ebx
0x180022697  jmp     short loc_1800226D4
0x180022699  mov     rsi, [rdi]
0x18002269c  test    rsi, rsi
0x18002269f  jz      short loc_1800226D0
0x1800226a1  mov     ecx, 1
0x1800226a6  call    qword ptr [rsi+8]
0x1800226a9  mov     ebx, eax
0x1800226ab  test    eax, eax
0x1800226ad  js      short loc_1800226D9
0x1800226af  call    qword ptr [rsi+38h]
0x1800226b2  mov     rcx, [rsi]; rguid
0x1800226b5  mov     r8d, 1
0x1800226bb  mov     rdx, rax
0x1800226be  call    sub_180022858
0x1800226c3  mov     ebx, eax
0x1800226c5  test    eax, eax
0x1800226c7  js      short loc_1800226D9
0x1800226c9  mov     rdx, cs:qword_1800A3748
0x1800226d0  add     rdi, 8
0x1800226d4  cmp     rdi, rdx
0x1800226d7  jb      short loc_180022699
0x1800226d9  test    ebx, ebx
0x1800226db  js      short loc_1800226F4
0x1800226dd  mov     rax, cs:qword_1800A47C0
0x1800226e4  test    rax, rax
0x1800226e7  jz      short loc_1800226F4
0x1800226e9  mov     rcx, cs:hModule
0x1800226f0  call    rax ; qword_1800A47C0
0x1800226f2  mov     ebx, eax
0x1800226f4  mov     ecx, ebp; Locale
0x1800226f6  call    cs:SetThreadLocale
0x1800226fc  mov     rbp, [rsp+28h+arg_8]
0x180022701  mov     rsi, [rsp+28h+arg_10]
0x180022706  mov     eax, ebx
0x180022708  mov     rbx, [rsp+28h+arg_0]
0x18002270d  add     rsp, 20h
0x180022711  pop     rdi
0x180022712  retn
```
