# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000a10c`
- end: `0x18000a1c3`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b300`

## callees

- `0x1800068ac`
- `0x18000a10c`

## import_xrefs

- `msvcrt!free` at `0x18000a163`
- `msvcrt!free` at `0x18000a192`
- `msvcrt!free` at `0x18000a163`
- `msvcrt!free` at `0x18000a192`
- `KERNEL32!DeleteCriticalSection` at `0x18000a17d`
- `KERNEL32!DeleteCriticalSection` at `0x18000a17d`
- `USER32!UnregisterClassA` at `0x18000a14d`
- `USER32!UnregisterClassA` at `0x18000a14d`

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
        JUMPOUT(0x18000A1C2LL);
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
0x18000a10c  mov     [rsp+arg_0], rbx
0x18000a111  mov     [rsp+arg_8], rsi
0x18000a116  push    rdi
0x18000a117  sub     rsp, 20h
0x18000a11b  mov     rbx, rcx
0x18000a11e  test    rcx, rcx
0x18000a121  jz      short loc_18000A189
0x18000a123  cmp     dword ptr [rcx], 48h ; 'H'
0x18000a126  jnz     short loc_18000A189
0x18000a128  mov     rsi, cs:hInstance
0x18000a12f  xor     edi, edi
0x18000a131  cmp     [rcx+40h], edi
0x18000a134  jle     short loc_18000A15A
0x18000a136  test    edi, edi
0x18000a138  js      short loc_18000A1B8
0x18000a13a  cmp     edi, [rbx+40h]
0x18000a13d  jge     short loc_18000A1B8
0x18000a13f  mov     rax, [rbx+38h]
0x18000a143  mov     rdx, rsi; hInstance
0x18000a146  movsxd  rcx, edi
0x18000a149  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000a14d  call    cs:__imp_UnregisterClassA
0x18000a153  inc     edi
0x18000a155  cmp     edi, [rbx+40h]
0x18000a158  jl      short loc_18000A136
0x18000a15a  mov     rcx, [rbx+38h]; Block
0x18000a15e  test    rcx, rcx
0x18000a161  jz      short loc_18000A171
0x18000a163  call    cs:__imp_free
0x18000a169  mov     qword ptr [rbx+38h], 0
0x18000a171  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a175  mov     qword ptr [rbx+40h], 0
0x18000a17d  call    cs:__imp_DeleteCriticalSection
0x18000a183  mov     dword ptr [rbx], 0
0x18000a189  mov     rcx, [rbx+38h]; Block
0x18000a18d  test    rcx, rcx
0x18000a190  jz      short loc_18000A1A0
0x18000a192  call    cs:__imp_free
0x18000a198  mov     qword ptr [rbx+38h], 0
0x18000a1a0  mov     rsi, [rsp+28h+arg_8]
0x18000a1a5  mov     qword ptr [rbx+40h], 0
0x18000a1ad  mov     rbx, [rsp+28h+arg_0]
0x18000a1b2  add     rsp, 20h
0x18000a1b6  pop     rdi
0x18000a1b7  retn
0x18000a1b8  mov     ecx, 0C000008Ch; unsigned int
0x18000a1bd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
