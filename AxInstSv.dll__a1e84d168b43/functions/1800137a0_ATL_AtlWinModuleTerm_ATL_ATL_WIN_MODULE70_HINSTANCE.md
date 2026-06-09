# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800137a0`
- end: `0x180013834`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013740`

## callees

- `0x1800137a0`
- `0x18001383c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013801`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013801`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013818`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013818`
- `USER32!UnregisterClassA` at `0x1800137e3`
- `USER32!UnregisterClassA` at `0x1800137e3`

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
0x1800137a0  push    rbx
0x1800137a2  push    rbp
0x1800137a3  push    rsi
0x1800137a4  push    rdi
0x1800137a5  sub     rsp, 28h
0x1800137a9  mov     rbp, rdx
0x1800137ac  mov     rbx, rcx
0x1800137af  test    rcx, rcx
0x1800137b2  jz      short loc_180013826
0x1800137b4  cmp     dword ptr [rcx], 0
0x1800137b7  jnz     short loc_1800137BD
0x1800137b9  xor     eax, eax
0x1800137bb  jmp     short loc_18001382B
0x1800137bd  cmp     dword ptr [rcx], 48h ; 'H'
0x1800137c0  jnz     short loc_180013826
0x1800137c2  xor     esi, esi
0x1800137c4  cmp     [rcx+40h], esi
0x1800137c7  jle     short loc_180013808
0x1800137c9  test    esi, esi
0x1800137cb  js      short loc_1800137F2
0x1800137cd  lea     rdi, [rbx+38h]
0x1800137d1  cmp     esi, [rdi+8]
0x1800137d4  jge     short loc_1800137F2
0x1800137d6  mov     rax, [rdi]
0x1800137d9  mov     rdx, rbp; hInstance
0x1800137dc  movsxd  rcx, esi
0x1800137df  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800137e3  call    cs:__imp_UnregisterClassA
0x1800137e9  inc     esi
0x1800137eb  cmp     esi, [rbx+40h]
0x1800137ee  jl      short loc_1800137C9
0x1800137f0  jmp     short loc_18001380C
0x1800137f2  xor     r9d, r9d; lpArguments
0x1800137f5  xor     r8d, r8d; nNumberOfArguments
0x1800137f8  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800137fd  lea     edx, [r9+1]; dwExceptionFlags
0x180013801  call    cs:__imp_RaiseException
0x180013807  int     3; Trap to Debugger
0x180013808  lea     rdi, [rcx+38h]
0x18001380c  mov     rcx, rdi
0x18001380f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180013814  lea     rcx, [rbx+8]; lpCriticalSection
0x180013818  call    cs:__imp_DeleteCriticalSection
0x18001381e  mov     dword ptr [rbx], 0
0x180013824  jmp     short loc_1800137B9
0x180013826  mov     eax, 80070057h
0x18001382b  add     rsp, 28h
0x18001382f  pop     rdi
0x180013830  pop     rsi
0x180013831  pop     rbp
0x180013832  pop     rbx
0x180013833  retn
```
