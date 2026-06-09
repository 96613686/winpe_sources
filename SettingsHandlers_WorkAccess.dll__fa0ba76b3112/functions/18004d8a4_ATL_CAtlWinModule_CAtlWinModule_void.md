# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18004d8a4`
- end: `0x18004d930`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180051460`

## callees

- `0x18004d8a4`
- `0x18004da40`
- `0x18004da7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d90d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d90d`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18004d8e2`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18004d8e2`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rbp
  int v4; // esi
  _QWORD *v5; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    v4 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v5 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v4 < 0 || (v5 = (_QWORD *)((char *)this + 56), v4 >= *((_DWORD *)this + 16)) )
        {
          ATL::_AtlRaiseException((unsigned int)this, a2);
          __debugbreak();
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v5 + 2LL * v4++), v3);
      }
      while ( v4 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x18004d8a4  push    rbx
0x18004d8a6  push    rbp
0x18004d8a7  push    rsi
0x18004d8a8  push    rdi
0x18004d8a9  sub     rsp, 28h
0x18004d8ad  mov     rbx, rcx
0x18004d8b0  test    rcx, rcx
0x18004d8b3  jz      short loc_18004D91F
0x18004d8b5  cmp     dword ptr [rcx], 48h ; 'H'
0x18004d8b8  jnz     short loc_18004D91F
0x18004d8ba  mov     rbp, cs:hInstance
0x18004d8c1  xor     esi, esi
0x18004d8c3  cmp     [rcx+40h], esi
0x18004d8c6  jle     short loc_18004D8FD
0x18004d8c8  test    esi, esi
0x18004d8ca  js      short loc_18004D8F7
0x18004d8cc  lea     rdi, [rbx+38h]
0x18004d8d0  cmp     esi, [rdi+8]
0x18004d8d3  jge     short loc_18004D8F7
0x18004d8d5  mov     rax, [rdi]
0x18004d8d8  mov     rdx, rbp; hInstance
0x18004d8db  movsxd  rcx, esi
0x18004d8de  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18004d8e2  call    cs:__imp_UnregisterClassA
0x18004d8e9  nop     dword ptr [rax+rax+00h]
0x18004d8ee  inc     esi
0x18004d8f0  cmp     esi, [rbx+40h]
0x18004d8f3  jl      short loc_18004D8C8
0x18004d8f5  jmp     short loc_18004D901
0x18004d8f7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18004d8fc  int     3; Trap to Debugger
0x18004d8fd  lea     rdi, [rcx+38h]
0x18004d901  mov     rcx, rdi
0x18004d904  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18004d909  lea     rcx, [rbx+8]; lpCriticalSection
0x18004d90d  call    cs:__imp_DeleteCriticalSection
0x18004d914  nop     dword ptr [rax+rax+00h]
0x18004d919  mov     dword ptr [rbx], 0
0x18004d91f  lea     rcx, [rbx+38h]
0x18004d923  add     rsp, 28h
0x18004d927  pop     rdi
0x18004d928  pop     rsi
0x18004d929  pop     rbp
0x18004d92a  pop     rbx
0x18004d92b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
