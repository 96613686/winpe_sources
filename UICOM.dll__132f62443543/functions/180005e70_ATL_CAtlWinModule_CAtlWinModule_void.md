# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180005e70`
- end: `0x180005f27`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006400`

## callees

- `0x180004e44`
- `0x180005e70`

## import_xrefs

- `msvcrt!free` at `0x180005ec7`
- `msvcrt!free` at `0x180005ef6`
- `msvcrt!free` at `0x180005ec7`
- `msvcrt!free` at `0x180005ef6`
- `KERNEL32!DeleteCriticalSection` at `0x180005ee1`
- `KERNEL32!DeleteCriticalSection` at `0x180005ee1`
- `USER32!UnregisterClassA` at `0x180005eb1`
- `USER32!UnregisterClassA` at `0x180005eb1`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rsi
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180005F26LL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v3);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180005e70  mov     [rsp+arg_0], rbx
0x180005e75  mov     [rsp+arg_8], rsi
0x180005e7a  push    rdi
0x180005e7b  sub     rsp, 20h
0x180005e7f  mov     rbx, rcx
0x180005e82  test    rcx, rcx
0x180005e85  jz      short loc_180005EED
0x180005e87  cmp     dword ptr [rcx], 48h ; 'H'
0x180005e8a  jnz     short loc_180005EED
0x180005e8c  mov     rsi, cs:hInstance
0x180005e93  xor     edi, edi
0x180005e95  cmp     [rcx+40h], edi
0x180005e98  jle     short loc_180005EBE
0x180005e9a  test    edi, edi
0x180005e9c  js      short loc_180005F1C
0x180005e9e  cmp     edi, [rbx+40h]
0x180005ea1  jge     short loc_180005F1C
0x180005ea3  mov     rax, [rbx+38h]
0x180005ea7  mov     rdx, rsi; hInstance
0x180005eaa  movsxd  rcx, edi
0x180005ead  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180005eb1  call    cs:__imp_UnregisterClassA
0x180005eb7  inc     edi
0x180005eb9  cmp     edi, [rbx+40h]
0x180005ebc  jl      short loc_180005E9A
0x180005ebe  mov     rcx, [rbx+38h]; Block
0x180005ec2  test    rcx, rcx
0x180005ec5  jz      short loc_180005ED5
0x180005ec7  call    cs:__imp_free
0x180005ecd  mov     qword ptr [rbx+38h], 0
0x180005ed5  lea     rcx, [rbx+8]; lpCriticalSection
0x180005ed9  mov     qword ptr [rbx+40h], 0
0x180005ee1  call    cs:__imp_DeleteCriticalSection
0x180005ee7  mov     dword ptr [rbx], 0
0x180005eed  mov     rcx, [rbx+38h]; Block
0x180005ef1  test    rcx, rcx
0x180005ef4  jz      short loc_180005F04
0x180005ef6  call    cs:__imp_free
0x180005efc  mov     qword ptr [rbx+38h], 0
0x180005f04  mov     rsi, [rsp+28h+arg_8]
0x180005f09  mov     qword ptr [rbx+40h], 0
0x180005f11  mov     rbx, [rsp+28h+arg_0]
0x180005f16  add     rsp, 20h
0x180005f1a  pop     rdi
0x180005f1b  retn
0x180005f1c  mov     ecx, 0C000008Ch; unsigned int
0x180005f21  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
