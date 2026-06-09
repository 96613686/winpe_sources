# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18003a95c`
- end: `0x18003a9f0`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a8fc`

## callees

- `0x18003a95c`
- `0x18003a9f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a9d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a9d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a9bd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a9bd`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18003a99f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18003a99f`

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
0x18003a95c  push    rbx
0x18003a95e  push    rbp
0x18003a95f  push    rsi
0x18003a960  push    rdi
0x18003a961  sub     rsp, 28h
0x18003a965  mov     rbp, rdx
0x18003a968  mov     rbx, rcx
0x18003a96b  test    rcx, rcx
0x18003a96e  jz      short loc_18003A9E2
0x18003a970  cmp     dword ptr [rcx], 0
0x18003a973  jnz     short loc_18003A979
0x18003a975  xor     eax, eax
0x18003a977  jmp     short loc_18003A9E7
0x18003a979  cmp     dword ptr [rcx], 48h ; 'H'
0x18003a97c  jnz     short loc_18003A9E2
0x18003a97e  xor     esi, esi
0x18003a980  cmp     [rcx+40h], esi
0x18003a983  jle     short loc_18003A9C4
0x18003a985  test    esi, esi
0x18003a987  js      short loc_18003A9AE
0x18003a989  lea     rdi, [rbx+38h]
0x18003a98d  cmp     esi, [rdi+8]
0x18003a990  jge     short loc_18003A9AE
0x18003a992  mov     rax, [rdi]
0x18003a995  mov     rdx, rbp; hInstance
0x18003a998  movsxd  rcx, esi
0x18003a99b  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18003a99f  call    cs:__imp_UnregisterClassA
0x18003a9a5  inc     esi
0x18003a9a7  cmp     esi, [rbx+40h]
0x18003a9aa  jl      short loc_18003A985
0x18003a9ac  jmp     short loc_18003A9C8
0x18003a9ae  xor     r9d, r9d; lpArguments
0x18003a9b1  xor     r8d, r8d; nNumberOfArguments
0x18003a9b4  mov     ecx, 0C000008Ch; dwExceptionCode
0x18003a9b9  lea     edx, [r9+1]; dwExceptionFlags
0x18003a9bd  call    cs:__imp_RaiseException
0x18003a9c3  int     3; Trap to Debugger
0x18003a9c4  lea     rdi, [rcx+38h]
0x18003a9c8  mov     rcx, rdi
0x18003a9cb  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003a9d0  lea     rcx, [rbx+8]; lpCriticalSection
0x18003a9d4  call    cs:__imp_DeleteCriticalSection
0x18003a9da  mov     dword ptr [rbx], 0
0x18003a9e0  jmp     short loc_18003A975
0x18003a9e2  mov     eax, 80070057h
0x18003a9e7  add     rsp, 28h
0x18003a9eb  pop     rdi
0x18003a9ec  pop     rsi
0x18003a9ed  pop     rbp
0x18003a9ee  pop     rbx
0x18003a9ef  retn
```
