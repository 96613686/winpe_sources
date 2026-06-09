# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000f568`
- end: `0x18000f61f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800132e0`

## callees

- `0x180008f7c`
- `0x18000f568`

## import_xrefs

- `msvcrt!free` at `0x18000f5bf`
- `msvcrt!free` at `0x18000f5ee`
- `msvcrt!free` at `0x18000f5bf`
- `msvcrt!free` at `0x18000f5ee`
- `KERNEL32!DeleteCriticalSection` at `0x18000f5d9`
- `KERNEL32!DeleteCriticalSection` at `0x18000f5d9`
- `USER32!UnregisterClassA` at `0x18000f5a9`
- `USER32!UnregisterClassA` at `0x18000f5a9`

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
        JUMPOUT(0x18000F61ELL);
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
0x18000f568  mov     [rsp+arg_0], rbx
0x18000f56d  mov     [rsp+arg_8], rsi
0x18000f572  push    rdi
0x18000f573  sub     rsp, 20h
0x18000f577  mov     rbx, rcx
0x18000f57a  test    rcx, rcx
0x18000f57d  jz      short loc_18000F5E5
0x18000f57f  cmp     dword ptr [rcx], 48h ; 'H'
0x18000f582  jnz     short loc_18000F5E5
0x18000f584  mov     rsi, cs:hInstance
0x18000f58b  xor     edi, edi
0x18000f58d  cmp     [rcx+40h], edi
0x18000f590  jle     short loc_18000F5B6
0x18000f592  test    edi, edi
0x18000f594  js      short loc_18000F614
0x18000f596  cmp     edi, [rbx+40h]
0x18000f599  jge     short loc_18000F614
0x18000f59b  mov     rax, [rbx+38h]
0x18000f59f  mov     rdx, rsi; hInstance
0x18000f5a2  movsxd  rcx, edi
0x18000f5a5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000f5a9  call    cs:__imp_UnregisterClassA
0x18000f5af  inc     edi
0x18000f5b1  cmp     edi, [rbx+40h]
0x18000f5b4  jl      short loc_18000F592
0x18000f5b6  mov     rcx, [rbx+38h]; Block
0x18000f5ba  test    rcx, rcx
0x18000f5bd  jz      short loc_18000F5CD
0x18000f5bf  call    cs:__imp_free
0x18000f5c5  mov     qword ptr [rbx+38h], 0
0x18000f5cd  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f5d1  mov     qword ptr [rbx+40h], 0
0x18000f5d9  call    cs:__imp_DeleteCriticalSection
0x18000f5df  mov     dword ptr [rbx], 0
0x18000f5e5  mov     rcx, [rbx+38h]; Block
0x18000f5e9  test    rcx, rcx
0x18000f5ec  jz      short loc_18000F5FC
0x18000f5ee  call    cs:__imp_free
0x18000f5f4  mov     qword ptr [rbx+38h], 0
0x18000f5fc  mov     rsi, [rsp+28h+arg_8]
0x18000f601  mov     qword ptr [rbx+40h], 0
0x18000f609  mov     rbx, [rsp+28h+arg_0]
0x18000f60e  add     rsp, 20h
0x18000f612  pop     rdi
0x18000f613  retn
0x18000f614  mov     ecx, 0C000008Ch; unsigned int
0x18000f619  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
