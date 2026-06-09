# DllMain

- ea: `0x18000fa84`
- end: `0x18000fb00`
- name: `DllMain`
- size: `124`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800153a4`

## callees

- `0x18000fa84`
- `0x18000fb08`
- `0x180084e40`
- `0x180086010`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v6; // esi
  __int64 i; // rbx
  unsigned int (__fastcall *v8)(HINSTANCE, _QWORD, LPVOID); // rax

  v6 = 1;
  for ( i = 0; i != 4; ++i )
  {
    v8 = (unsigned int (__fastcall *)(HINSTANCE, _QWORD, LPVOID))qword_1801B6950[5 * i];
    if ( v8 )
      v6 = v8(hinstDLL, fdwReason, lpvReserved) != 0 ? v6 : 0;
  }
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hInst = hinstDLL;
      McGenEventRegister_EventRegister();
    }
  }
  else if ( !lpvReserved )
  {
    McGenEventUnregister_EventUnregister();
  }
  return v6;
}

```

## disassembly

```asm
0x18000fa84  push    rbx
0x18000fa86  push    rbp
0x18000fa87  push    rsi
0x18000fa88  push    rdi
0x18000fa89  push    r14
0x18000fa8b  sub     rsp, 20h
0x18000fa8f  mov     r14, r8
0x18000fa92  mov     edi, edx
0x18000fa94  mov     rbp, rcx
0x18000fa97  mov     esi, 1
0x18000fa9c  xor     ebx, ebx
0x18000fa9e  lea     rax, [rbx+rbx*4]
0x18000faa2  lea     rcx, qword_1801B6950
0x18000faa9  mov     rax, [rcx+rax*8]
0x18000faad  test    rax, rax
0x18000fab0  jnz     short loc_18000FADF
0x18000fab2  inc     rbx
0x18000fab5  cmp     rbx, 4
0x18000fab9  jnz     short loc_18000FA9E
0x18000fabb  test    edi, edi
0x18000fabd  jz      short loc_18000FAF4
0x18000fabf  cmp     edi, 1
0x18000fac2  jz      short loc_18000FAD1
0x18000fac4  mov     eax, esi
0x18000fac6  add     rsp, 20h
0x18000faca  pop     r14
0x18000facc  pop     rdi
0x18000facd  pop     rsi
0x18000face  pop     rbp
0x18000facf  pop     rbx
0x18000fad0  retn
0x18000fad1  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * g_hInst
0x18000fad8  call    McGenEventRegister_EventRegister
0x18000fadd  jmp     short loc_18000FAC4
0x18000fadf  mov     r8, r14
0x18000fae2  mov     edx, edi
0x18000fae4  mov     rcx, rbp
0x18000fae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faec  neg     eax
0x18000faee  sbb     ecx, ecx
0x18000faf0  and     esi, ecx
0x18000faf2  jmp     short loc_18000FAB2
0x18000faf4  test    r14, r14
0x18000faf7  jnz     short loc_18000FAC4
0x18000faf9  call    McGenEventUnregister_EventUnregister
0x18000fafe  jmp     short loc_18000FAC4
```
