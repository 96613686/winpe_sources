# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800100c4`
- end: `0x180010158`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001002c`

## callees

- `0x1800100c4`
- `0x1800101dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001013c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001013c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010125`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010125`
- `USER32!UnregisterClassA` at `0x180010107`
- `USER32!UnregisterClassA` at `0x180010107`

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
0x1800100c4  push    rbx
0x1800100c6  push    rbp
0x1800100c7  push    rsi
0x1800100c8  push    rdi
0x1800100c9  sub     rsp, 28h
0x1800100cd  mov     rbp, rdx
0x1800100d0  mov     rbx, rcx
0x1800100d3  test    rcx, rcx
0x1800100d6  jz      short loc_18001014A
0x1800100d8  cmp     dword ptr [rcx], 0
0x1800100db  jnz     short loc_1800100E1
0x1800100dd  xor     eax, eax
0x1800100df  jmp     short loc_18001014F
0x1800100e1  cmp     dword ptr [rcx], 48h ; 'H'
0x1800100e4  jnz     short loc_18001014A
0x1800100e6  xor     esi, esi
0x1800100e8  cmp     [rcx+40h], esi
0x1800100eb  jle     short loc_18001012C
0x1800100ed  test    esi, esi
0x1800100ef  js      short loc_180010116
0x1800100f1  lea     rdi, [rbx+38h]
0x1800100f5  cmp     esi, [rdi+8]
0x1800100f8  jge     short loc_180010116
0x1800100fa  mov     rax, [rdi]
0x1800100fd  mov     rdx, rbp; hInstance
0x180010100  movsxd  rcx, esi
0x180010103  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180010107  call    cs:__imp_UnregisterClassA
0x18001010d  inc     esi
0x18001010f  cmp     esi, [rbx+40h]
0x180010112  jl      short loc_1800100ED
0x180010114  jmp     short loc_180010130
0x180010116  xor     r9d, r9d; lpArguments
0x180010119  xor     r8d, r8d; nNumberOfArguments
0x18001011c  mov     ecx, 0C000008Ch; dwExceptionCode
0x180010121  lea     edx, [r9+1]; dwExceptionFlags
0x180010125  call    cs:__imp_RaiseException
0x18001012b  int     3; Trap to Debugger
0x18001012c  lea     rdi, [rcx+38h]
0x180010130  mov     rcx, rdi
0x180010133  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180010138  lea     rcx, [rbx+8]; lpCriticalSection
0x18001013c  call    cs:__imp_DeleteCriticalSection
0x180010142  mov     dword ptr [rbx], 0
0x180010148  jmp     short loc_1800100DD
0x18001014a  mov     eax, 80070057h
0x18001014f  add     rsp, 28h
0x180010153  pop     rdi
0x180010154  pop     rsi
0x180010155  pop     rbp
0x180010156  pop     rbx
0x180010157  retn
```
