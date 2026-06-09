# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000b2c4`
- end: `0x18000b37b`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c2b0`

## callees

- `0x18000701c`
- `0x18000b2c4`

## import_xrefs

- `msvcrt!free` at `0x18000b31b`
- `msvcrt!free` at `0x18000b34a`
- `msvcrt!free` at `0x18000b31b`
- `msvcrt!free` at `0x18000b34a`
- `KERNEL32!DeleteCriticalSection` at `0x18000b335`
- `KERNEL32!DeleteCriticalSection` at `0x18000b335`
- `USER32!UnregisterClassA` at `0x18000b305`
- `USER32!UnregisterClassA` at `0x18000b305`

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
    v3 = hModule;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x18000B37ALL);
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
0x18000b2c4  mov     [rsp+arg_0], rbx
0x18000b2c9  mov     [rsp+arg_8], rsi
0x18000b2ce  push    rdi
0x18000b2cf  sub     rsp, 20h
0x18000b2d3  mov     rbx, rcx
0x18000b2d6  test    rcx, rcx
0x18000b2d9  jz      short loc_18000B341
0x18000b2db  cmp     dword ptr [rcx], 48h ; 'H'
0x18000b2de  jnz     short loc_18000B341
0x18000b2e0  mov     rsi, cs:hModule
0x18000b2e7  xor     edi, edi
0x18000b2e9  cmp     [rcx+40h], edi
0x18000b2ec  jle     short loc_18000B312
0x18000b2ee  test    edi, edi
0x18000b2f0  js      short loc_18000B370
0x18000b2f2  cmp     edi, [rbx+40h]
0x18000b2f5  jge     short loc_18000B370
0x18000b2f7  mov     rax, [rbx+38h]
0x18000b2fb  mov     rdx, rsi; hInstance
0x18000b2fe  movsxd  rcx, edi
0x18000b301  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000b305  call    cs:__imp_UnregisterClassA
0x18000b30b  inc     edi
0x18000b30d  cmp     edi, [rbx+40h]
0x18000b310  jl      short loc_18000B2EE
0x18000b312  mov     rcx, [rbx+38h]; Block
0x18000b316  test    rcx, rcx
0x18000b319  jz      short loc_18000B329
0x18000b31b  call    cs:__imp_free
0x18000b321  mov     qword ptr [rbx+38h], 0
0x18000b329  lea     rcx, [rbx+8]; lpCriticalSection
0x18000b32d  mov     qword ptr [rbx+40h], 0
0x18000b335  call    cs:__imp_DeleteCriticalSection
0x18000b33b  mov     dword ptr [rbx], 0
0x18000b341  mov     rcx, [rbx+38h]; Block
0x18000b345  test    rcx, rcx
0x18000b348  jz      short loc_18000B358
0x18000b34a  call    cs:__imp_free
0x18000b350  mov     qword ptr [rbx+38h], 0
0x18000b358  mov     rsi, [rsp+28h+arg_8]
0x18000b35d  mov     qword ptr [rbx+40h], 0
0x18000b365  mov     rbx, [rsp+28h+arg_0]
0x18000b36a  add     rsp, 20h
0x18000b36e  pop     rdi
0x18000b36f  retn
0x18000b370  mov     ecx, 0C000008Ch; unsigned int
0x18000b375  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
