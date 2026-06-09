# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180020340`
- end: `0x1800203d4`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800202a8`

## callees

- `0x180020340`
- `0x1800204a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800203b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800203b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800203a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800203a1`
- `USER32!UnregisterClassA` at `0x180020383`
- `USER32!UnregisterClassA` at `0x180020383`

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
0x180020340  push    rbx
0x180020342  push    rbp
0x180020343  push    rsi
0x180020344  push    rdi
0x180020345  sub     rsp, 28h
0x180020349  mov     rbp, rdx
0x18002034c  mov     rbx, rcx
0x18002034f  test    rcx, rcx
0x180020352  jz      short loc_1800203C6
0x180020354  cmp     dword ptr [rcx], 0
0x180020357  jnz     short loc_18002035D
0x180020359  xor     eax, eax
0x18002035b  jmp     short loc_1800203CB
0x18002035d  cmp     dword ptr [rcx], 48h ; 'H'
0x180020360  jnz     short loc_1800203C6
0x180020362  xor     esi, esi
0x180020364  cmp     [rcx+40h], esi
0x180020367  jle     short loc_1800203A8
0x180020369  test    esi, esi
0x18002036b  js      short loc_180020392
0x18002036d  lea     rdi, [rbx+38h]
0x180020371  cmp     esi, [rdi+8]
0x180020374  jge     short loc_180020392
0x180020376  mov     rax, [rdi]
0x180020379  mov     rdx, rbp; hInstance
0x18002037c  movsxd  rcx, esi
0x18002037f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180020383  call    cs:__imp_UnregisterClassA
0x180020389  inc     esi
0x18002038b  cmp     esi, [rbx+40h]
0x18002038e  jl      short loc_180020369
0x180020390  jmp     short loc_1800203AC
0x180020392  xor     r9d, r9d; lpArguments
0x180020395  xor     r8d, r8d; nNumberOfArguments
0x180020398  mov     ecx, 0C000008Ch; dwExceptionCode
0x18002039d  lea     edx, [r9+1]; dwExceptionFlags
0x1800203a1  call    cs:__imp_RaiseException
0x1800203a7  int     3; Trap to Debugger
0x1800203a8  lea     rdi, [rcx+38h]
0x1800203ac  mov     rcx, rdi
0x1800203af  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800203b4  lea     rcx, [rbx+8]; lpCriticalSection
0x1800203b8  call    cs:__imp_DeleteCriticalSection
0x1800203be  mov     dword ptr [rbx], 0
0x1800203c4  jmp     short loc_180020359
0x1800203c6  mov     eax, 80070057h
0x1800203cb  add     rsp, 28h
0x1800203cf  pop     rdi
0x1800203d0  pop     rsi
0x1800203d1  pop     rbp
0x1800203d2  pop     rbx
0x1800203d3  retn
```
