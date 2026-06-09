# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x140011c00`
- end: `0x140011cb7`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012840`

## callees

- `0x1400062fc`
- `0x140011c00`

## import_xrefs

- `USER32!UnregisterClassA` at `0x140011c41`
- `USER32!UnregisterClassA` at `0x140011c41`
- `msvcrt!free` at `0x140011c57`
- `msvcrt!free` at `0x140011c86`
- `msvcrt!free` at `0x140011c57`
- `msvcrt!free` at `0x140011c86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011c71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011c71`

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
        JUMPOUT(0x140011CB6LL);
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
0x140011c00  mov     [rsp+arg_0], rbx
0x140011c05  mov     [rsp+arg_8], rsi
0x140011c0a  push    rdi
0x140011c0b  sub     rsp, 20h
0x140011c0f  mov     rbx, rcx
0x140011c12  test    rcx, rcx
0x140011c15  jz      short loc_140011C7D
0x140011c17  cmp     dword ptr [rcx], 48h ; 'H'
0x140011c1a  jnz     short loc_140011C7D
0x140011c1c  mov     rsi, cs:hInstance
0x140011c23  xor     edi, edi
0x140011c25  cmp     [rcx+40h], edi
0x140011c28  jle     short loc_140011C4E
0x140011c2a  test    edi, edi
0x140011c2c  js      short loc_140011CAC
0x140011c2e  cmp     edi, [rbx+40h]
0x140011c31  jge     short loc_140011CAC
0x140011c33  mov     rax, [rbx+38h]
0x140011c37  mov     rdx, rsi; hInstance
0x140011c3a  movsxd  rcx, edi
0x140011c3d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x140011c41  call    cs:__imp_UnregisterClassA
0x140011c47  inc     edi
0x140011c49  cmp     edi, [rbx+40h]
0x140011c4c  jl      short loc_140011C2A
0x140011c4e  mov     rcx, [rbx+38h]; Block
0x140011c52  test    rcx, rcx
0x140011c55  jz      short loc_140011C65
0x140011c57  call    cs:__imp_free
0x140011c5d  mov     qword ptr [rbx+38h], 0
0x140011c65  lea     rcx, [rbx+8]; lpCriticalSection
0x140011c69  mov     qword ptr [rbx+40h], 0
0x140011c71  call    cs:__imp_DeleteCriticalSection
0x140011c77  mov     dword ptr [rbx], 0
0x140011c7d  mov     rcx, [rbx+38h]; Block
0x140011c81  test    rcx, rcx
0x140011c84  jz      short loc_140011C94
0x140011c86  call    cs:__imp_free
0x140011c8c  mov     qword ptr [rbx+38h], 0
0x140011c94  mov     rsi, [rsp+28h+arg_8]
0x140011c99  mov     qword ptr [rbx+40h], 0
0x140011ca1  mov     rbx, [rsp+28h+arg_0]
0x140011ca6  add     rsp, 20h
0x140011caa  pop     rdi
0x140011cab  retn
0x140011cac  mov     ecx, 0C000008Ch; unsigned int
0x140011cb1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
