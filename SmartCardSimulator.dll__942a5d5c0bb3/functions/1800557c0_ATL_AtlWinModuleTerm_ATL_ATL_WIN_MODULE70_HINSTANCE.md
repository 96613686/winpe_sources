# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800557c0`
- end: `0x180055854`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180055760`

## callees

- `0x1800557c0`
- `0x18005585c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055838`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055821`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055821`
- `USER32!UnregisterClassA` at `0x180055803`
- `USER32!UnregisterClassA` at `0x180055803`

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
0x1800557c0  push    rbx
0x1800557c2  push    rbp
0x1800557c3  push    rsi
0x1800557c4  push    rdi
0x1800557c5  sub     rsp, 28h
0x1800557c9  mov     rbp, rdx
0x1800557cc  mov     rbx, rcx
0x1800557cf  test    rcx, rcx
0x1800557d2  jz      short loc_180055846
0x1800557d4  cmp     dword ptr [rcx], 0
0x1800557d7  jnz     short loc_1800557DD
0x1800557d9  xor     eax, eax
0x1800557db  jmp     short loc_18005584B
0x1800557dd  cmp     dword ptr [rcx], 48h ; 'H'
0x1800557e0  jnz     short loc_180055846
0x1800557e2  xor     esi, esi
0x1800557e4  cmp     [rcx+40h], esi
0x1800557e7  jle     short loc_180055828
0x1800557e9  test    esi, esi
0x1800557eb  js      short loc_180055812
0x1800557ed  lea     rdi, [rbx+38h]
0x1800557f1  cmp     esi, [rdi+8]
0x1800557f4  jge     short loc_180055812
0x1800557f6  mov     rax, [rdi]
0x1800557f9  mov     rdx, rbp; hInstance
0x1800557fc  movsxd  rcx, esi
0x1800557ff  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180055803  call    cs:__imp_UnregisterClassA
0x180055809  inc     esi
0x18005580b  cmp     esi, [rbx+40h]
0x18005580e  jl      short loc_1800557E9
0x180055810  jmp     short loc_18005582C
0x180055812  xor     r9d, r9d; lpArguments
0x180055815  xor     r8d, r8d; nNumberOfArguments
0x180055818  mov     ecx, 0C000008Ch; dwExceptionCode
0x18005581d  lea     edx, [r9+1]; dwExceptionFlags
0x180055821  call    cs:__imp_RaiseException
0x180055827  int     3; Trap to Debugger
0x180055828  lea     rdi, [rcx+38h]
0x18005582c  mov     rcx, rdi
0x18005582f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180055834  lea     rcx, [rbx+8]; lpCriticalSection
0x180055838  call    cs:__imp_DeleteCriticalSection
0x18005583e  mov     dword ptr [rbx], 0
0x180055844  jmp     short loc_1800557D9
0x180055846  mov     eax, 80070057h
0x18005584b  add     rsp, 28h
0x18005584f  pop     rdi
0x180055850  pop     rsi
0x180055851  pop     rbp
0x180055852  pop     rbx
0x180055853  retn
```
