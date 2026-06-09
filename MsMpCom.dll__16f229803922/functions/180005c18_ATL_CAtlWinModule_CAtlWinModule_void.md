# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180005c18`
- end: `0x180005ccf`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009cb0`

## callees

- `0x180002444`
- `0x180005c18`

## import_xrefs

- `msvcrt!free` at `0x180005c6f`
- `msvcrt!free` at `0x180005c9e`
- `msvcrt!free` at `0x180005c6f`
- `msvcrt!free` at `0x180005c9e`
- `KERNEL32!DeleteCriticalSection` at `0x180005c89`
- `KERNEL32!DeleteCriticalSection` at `0x180005c89`
- `USER32!UnregisterClassA` at `0x180005c59`
- `USER32!UnregisterClassA` at `0x180005c59`

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
        JUMPOUT(0x180005CCELL);
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
0x180005c18  mov     [rsp+arg_0], rbx
0x180005c1d  mov     [rsp+arg_8], rsi
0x180005c22  push    rdi
0x180005c23  sub     rsp, 20h
0x180005c27  mov     rbx, rcx
0x180005c2a  test    rcx, rcx
0x180005c2d  jz      short loc_180005C95
0x180005c2f  cmp     dword ptr [rcx], 48h ; 'H'
0x180005c32  jnz     short loc_180005C95
0x180005c34  mov     rsi, cs:hInstance
0x180005c3b  xor     edi, edi
0x180005c3d  cmp     [rcx+40h], edi
0x180005c40  jle     short loc_180005C66
0x180005c42  test    edi, edi
0x180005c44  js      short loc_180005CC4
0x180005c46  cmp     edi, [rbx+40h]
0x180005c49  jge     short loc_180005CC4
0x180005c4b  mov     rax, [rbx+38h]
0x180005c4f  mov     rdx, rsi; hInstance
0x180005c52  movsxd  rcx, edi
0x180005c55  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180005c59  call    cs:__imp_UnregisterClassA
0x180005c5f  inc     edi
0x180005c61  cmp     edi, [rbx+40h]
0x180005c64  jl      short loc_180005C42
0x180005c66  mov     rcx, [rbx+38h]; Block
0x180005c6a  test    rcx, rcx
0x180005c6d  jz      short loc_180005C7D
0x180005c6f  call    cs:__imp_free
0x180005c75  mov     qword ptr [rbx+38h], 0
0x180005c7d  lea     rcx, [rbx+8]; lpCriticalSection
0x180005c81  mov     qword ptr [rbx+40h], 0
0x180005c89  call    cs:__imp_DeleteCriticalSection
0x180005c8f  mov     dword ptr [rbx], 0
0x180005c95  mov     rcx, [rbx+38h]; Block
0x180005c99  test    rcx, rcx
0x180005c9c  jz      short loc_180005CAC
0x180005c9e  call    cs:__imp_free
0x180005ca4  mov     qword ptr [rbx+38h], 0
0x180005cac  mov     rsi, [rsp+28h+arg_8]
0x180005cb1  mov     qword ptr [rbx+40h], 0
0x180005cb9  mov     rbx, [rsp+28h+arg_0]
0x180005cbe  add     rsp, 20h
0x180005cc2  pop     rdi
0x180005cc3  retn
0x180005cc4  mov     ecx, 0C000008Ch; unsigned int
0x180005cc9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
