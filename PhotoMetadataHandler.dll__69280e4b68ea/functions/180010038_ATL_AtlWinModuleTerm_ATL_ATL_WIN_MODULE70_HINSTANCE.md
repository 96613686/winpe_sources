# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180010038`
- end: `0x1800100ce`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `150`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001000c`

## callees

- `0x180010038`
- `0x1800100d4`
- `0x18001af5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010079`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010079`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x1800100a7`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x1800100a7`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  int v5; // esi
  _QWORD *v6; // rdi

  if ( a1 )
  {
    if ( !*(_DWORD *)a1 )
      return 0;
    if ( *(_DWORD *)a1 == 72 )
    {
      v5 = 0;
      if ( *((int *)a1 + 16) > 0 )
      {
        do
        {
          if ( v5 < 0 || (v6 = (_QWORD *)((char *)a1 + 56), v5 >= *((_DWORD *)a1 + 16)) )
          {
            ATL::_AtlRaiseException(0xC000008C, (unsigned int)a2);
            __debugbreak();
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
      }
      else
      {
        v6 = (_QWORD *)((char *)a1 + 56);
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v6);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
      *(_DWORD *)a1 = 0;
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180010038  push    rbx
0x18001003a  push    rbp
0x18001003b  push    rsi
0x18001003c  push    rdi
0x18001003d  sub     rsp, 28h
0x180010041  mov     rbp, rdx
0x180010044  mov     rbx, rcx
0x180010047  test    rcx, rcx
0x18001004a  jz      short loc_1800100C7
0x18001004c  cmp     dword ptr [rcx], 0
0x18001004f  jnz     short loc_18001005D
0x180010051  xor     eax, eax
0x180010053  add     rsp, 28h
0x180010057  pop     rdi
0x180010058  pop     rsi
0x180010059  pop     rbp
0x18001005a  pop     rbx
0x18001005b  retn
0x18001005d  cmp     dword ptr [rcx], 48h ; 'H'
0x180010060  jnz     short loc_1800100C7
0x180010062  xor     esi, esi
0x180010064  cmp     [rcx+40h], esi
0x180010067  jg      short loc_18001008D
0x180010069  lea     rdi, [rcx+38h]
0x18001006d  mov     rcx, rdi
0x180010070  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180010075  lea     rcx, [rbx+8]; lpCriticalSection
0x180010079  call    cs:__imp_DeleteCriticalSection
0x180010080  nop     dword ptr [rax+rax+00h]
0x180010085  mov     dword ptr [rbx], 0
0x18001008b  jmp     short loc_180010051
0x18001008d  test    esi, esi
0x18001008f  js      short loc_1800100BC
0x180010091  lea     rdi, [rbx+38h]
0x180010095  cmp     esi, [rdi+8]
0x180010098  jge     short loc_1800100BC
0x18001009a  mov     rax, [rdi]
0x18001009d  mov     rdx, rbp; hInstance
0x1800100a0  movsxd  rcx, esi
0x1800100a3  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800100a7  call    cs:__imp_UnregisterClassA
0x1800100ae  nop     dword ptr [rax+rax+00h]
0x1800100b3  inc     esi
0x1800100b5  cmp     esi, [rbx+40h]
0x1800100b8  jl      short loc_18001008D
0x1800100ba  jmp     short loc_18001006D
0x1800100bc  mov     ecx, 0C000008Ch; unsigned int
0x1800100c1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800100c6  int     3; Trap to Debugger
0x1800100c7  mov     eax, 80070057h
0x1800100cc  jmp     short loc_180010053
```
