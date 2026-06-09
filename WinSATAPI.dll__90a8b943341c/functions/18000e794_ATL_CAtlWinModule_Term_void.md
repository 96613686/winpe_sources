# ATL::CAtlWinModule::Term(void)

- ea: `0x18000e794`
- end: `0x18000e83d`
- name: `?Term@CAtlWinModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032750`

## callees

- `0x18000e794`
- `0x1800112a0`
- `0x18001a3ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e807`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e807`
- `USER32!UnregisterClassA` at `0x18000e7e3`
- `USER32!UnregisterClassA` at `0x18000e7e3`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::Term(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // r14
  int v4; // ebp
  __int64 v5; // rsi

  if ( this )
  {
    v3 = hModule;
    if ( *(_DWORD *)this == 72 )
    {
      v4 = 0;
      if ( *((int *)this + 16) > 0 )
      {
        v5 = 0;
        do
        {
          if ( v5 < 0 || v4 >= *((_DWORD *)this + 16) )
          {
            ATL::_AtlRaiseException(0xC000008C, a2);
            JUMPOUT(0x18000E83CLL);
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(v5 + *((_QWORD *)this + 7)), v3);
          ++v4;
          v5 += 2;
        }
        while ( v4 < *((_DWORD *)this + 16) );
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      *(_DWORD *)this = 0;
    }
  }
}

```

## disassembly

```asm
0x18000e794  test    rcx, rcx
0x18000e797  jz      locret_18000E830
0x18000e79d  mov     rax, rsp
0x18000e7a0  mov     [rax+8], rbx
0x18000e7a4  mov     [rax+10h], rbp
0x18000e7a8  mov     [rax+18h], rsi
0x18000e7ac  mov     [rax+20h], rdi
0x18000e7b0  push    r14
0x18000e7b2  sub     rsp, 20h
0x18000e7b6  cmp     dword ptr [rcx], 48h ; 'H'
0x18000e7b9  mov     rbx, rcx
0x18000e7bc  mov     r14, cs:hModule
0x18000e7c3  jnz     short loc_18000E816
0x18000e7c5  xor     ebp, ebp
0x18000e7c7  cmp     [rcx+40h], ebp
0x18000e7ca  jle     short loc_18000E7FA
0x18000e7cc  xor     esi, esi
0x18000e7ce  test    rsi, rsi
0x18000e7d1  js      short loc_18000E832
0x18000e7d3  cmp     ebp, [rbx+40h]
0x18000e7d6  jge     short loc_18000E832
0x18000e7d8  mov     rax, [rbx+38h]
0x18000e7dc  mov     rdx, r14; hInstance
0x18000e7df  movzx   ecx, word ptr [rsi+rax]; lpClassName
0x18000e7e3  call    cs:__imp_UnregisterClassA
0x18000e7ea  nop     dword ptr [rax+rax+00h]
0x18000e7ef  inc     ebp
0x18000e7f1  add     rsi, 2
0x18000e7f5  cmp     ebp, [rbx+40h]
0x18000e7f8  jl      short loc_18000E7CE
0x18000e7fa  lea     rcx, [rbx+38h]
0x18000e7fe  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000e803  lea     rcx, [rbx+8]; lpCriticalSection
0x18000e807  call    cs:__imp_DeleteCriticalSection
0x18000e80e  nop     dword ptr [rax+rax+00h]
0x18000e813  and     dword ptr [rbx], 0
0x18000e816  mov     rbx, [rsp+28h+arg_0]
0x18000e81b  mov     rbp, [rsp+28h+arg_8]
0x18000e820  mov     rsi, [rsp+28h+arg_10]
0x18000e825  mov     rdi, [rsp+28h+arg_18]
0x18000e82a  add     rsp, 20h
0x18000e82e  pop     r14
0x18000e830  retn
0x18000e832  mov     ecx, 0C000008Ch; unsigned int
0x18000e837  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
