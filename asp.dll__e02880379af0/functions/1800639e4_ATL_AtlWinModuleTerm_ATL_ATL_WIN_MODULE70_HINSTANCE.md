# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800639e4`
- end: `0x180063a78`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d9b4`

## callees

- `0x1800639e4`
- `0x180063a80`

## import_xrefs

- `USER32!UnregisterClassA` at `0x180063a27`
- `USER32!UnregisterClassA` at `0x180063a27`
- `KERNEL32!RaiseException` at `0x180063a45`
- `KERNEL32!RaiseException` at `0x180063a45`
- `KERNEL32!DeleteCriticalSection` at `0x180063a5c`
- `KERNEL32!DeleteCriticalSection` at `0x180063a5c`

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
0x1800639e4  push    rbx
0x1800639e6  push    rbp
0x1800639e7  push    rsi
0x1800639e8  push    rdi
0x1800639e9  sub     rsp, 28h
0x1800639ed  mov     rbp, rdx
0x1800639f0  mov     rbx, rcx
0x1800639f3  test    rcx, rcx
0x1800639f6  jz      short loc_180063A6A
0x1800639f8  cmp     dword ptr [rcx], 0
0x1800639fb  jnz     short loc_180063A01
0x1800639fd  xor     eax, eax
0x1800639ff  jmp     short loc_180063A6F
0x180063a01  cmp     dword ptr [rcx], 48h ; 'H'
0x180063a04  jnz     short loc_180063A6A
0x180063a06  xor     esi, esi
0x180063a08  cmp     [rcx+40h], esi
0x180063a0b  jle     short loc_180063A4C
0x180063a0d  test    esi, esi
0x180063a0f  js      short loc_180063A36
0x180063a11  lea     rdi, [rbx+38h]
0x180063a15  cmp     esi, [rdi+8]
0x180063a18  jge     short loc_180063A36
0x180063a1a  mov     rax, [rdi]
0x180063a1d  mov     rdx, rbp; hInstance
0x180063a20  movsxd  rcx, esi
0x180063a23  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180063a27  call    cs:__imp_UnregisterClassA
0x180063a2d  inc     esi
0x180063a2f  cmp     esi, [rbx+40h]
0x180063a32  jl      short loc_180063A0D
0x180063a34  jmp     short loc_180063A50
0x180063a36  xor     r9d, r9d; lpArguments
0x180063a39  xor     r8d, r8d; nNumberOfArguments
0x180063a3c  mov     ecx, 0C000008Ch; dwExceptionCode
0x180063a41  lea     edx, [r9+1]; dwExceptionFlags
0x180063a45  call    cs:__imp_RaiseException
0x180063a4b  int     3; Trap to Debugger
0x180063a4c  lea     rdi, [rcx+38h]
0x180063a50  mov     rcx, rdi
0x180063a53  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180063a58  lea     rcx, [rbx+8]; lpCriticalSection
0x180063a5c  call    cs:__imp_DeleteCriticalSection
0x180063a62  mov     dword ptr [rbx], 0
0x180063a68  jmp     short loc_1800639FD
0x180063a6a  mov     eax, 80070057h
0x180063a6f  add     rsp, 28h
0x180063a73  pop     rdi
0x180063a74  pop     rsi
0x180063a75  pop     rbp
0x180063a76  pop     rbx
0x180063a77  retn
```
