# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x14001513c`
- end: `0x1400151d0`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400150dc`

## callees

- `0x14001513c`
- `0x1400151d8`

## import_xrefs

- `KERNEL32!RaiseException` at `0x14001519d`
- `KERNEL32!RaiseException` at `0x14001519d`
- `KERNEL32!DeleteCriticalSection` at `0x1400151b4`
- `KERNEL32!DeleteCriticalSection` at `0x1400151b4`
- `USER32!UnregisterClassA` at `0x14001517f`
- `USER32!UnregisterClassA` at `0x14001517f`

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
      if ( *((int *)a1 + 16) <= 0 )
      {
        v6 = (_QWORD *)((char *)a1 + 56);
      }
      else
      {
        do
        {
          if ( v5 < 0 || (v6 = (_QWORD *)((char *)a1 + 56), v5 >= *((_DWORD *)a1 + 16)) )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            __debugbreak();
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
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
0x14001513c  push    rbx
0x14001513e  push    rbp
0x14001513f  push    rsi
0x140015140  push    rdi
0x140015141  sub     rsp, 28h
0x140015145  mov     rbp, rdx
0x140015148  mov     rbx, rcx
0x14001514b  test    rcx, rcx
0x14001514e  jz      short loc_1400151C2
0x140015150  cmp     dword ptr [rcx], 0
0x140015153  jnz     short loc_140015159
0x140015155  xor     eax, eax
0x140015157  jmp     short loc_1400151C7
0x140015159  cmp     dword ptr [rcx], 48h ; 'H'
0x14001515c  jnz     short loc_1400151C2
0x14001515e  xor     esi, esi
0x140015160  cmp     [rcx+40h], esi
0x140015163  jle     short loc_1400151A4
0x140015165  test    esi, esi
0x140015167  js      short loc_14001518E
0x140015169  lea     rdi, [rbx+38h]
0x14001516d  cmp     esi, [rdi+8]
0x140015170  jge     short loc_14001518E
0x140015172  mov     rax, [rdi]
0x140015175  mov     rdx, rbp; hInstance
0x140015178  movsxd  rcx, esi
0x14001517b  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14001517f  call    cs:__imp_UnregisterClassA
0x140015185  inc     esi
0x140015187  cmp     esi, [rbx+40h]
0x14001518a  jl      short loc_140015165
0x14001518c  jmp     short loc_1400151A8
0x14001518e  xor     r9d, r9d; lpArguments
0x140015191  xor     r8d, r8d; nNumberOfArguments
0x140015194  mov     ecx, 0C000008Ch; dwExceptionCode
0x140015199  lea     edx, [r9+1]; dwExceptionFlags
0x14001519d  call    cs:__imp_RaiseException
0x1400151a3  int     3; Trap to Debugger
0x1400151a4  lea     rdi, [rcx+38h]
0x1400151a8  mov     rcx, rdi
0x1400151ab  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1400151b0  lea     rcx, [rbx+8]; lpCriticalSection
0x1400151b4  call    cs:__imp_DeleteCriticalSection
0x1400151ba  mov     dword ptr [rbx], 0
0x1400151c0  jmp     short loc_140015155
0x1400151c2  mov     eax, 80070057h
0x1400151c7  add     rsp, 28h
0x1400151cb  pop     rdi
0x1400151cc  pop     rsi
0x1400151cd  pop     rbp
0x1400151ce  pop     rbx
0x1400151cf  retn
```
