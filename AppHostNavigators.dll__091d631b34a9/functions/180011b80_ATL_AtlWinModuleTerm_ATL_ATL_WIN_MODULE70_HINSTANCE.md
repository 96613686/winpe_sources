# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180011b80`
- end: `0x180011c14`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011b20`

## callees

- `0x180011b80`
- `0x180011c1c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180011be1`
- `KERNEL32!RaiseException` at `0x180011be1`
- `KERNEL32!DeleteCriticalSection` at `0x180011bf8`
- `KERNEL32!DeleteCriticalSection` at `0x180011bf8`
- `USER32!UnregisterClassA` at `0x180011bc3`
- `USER32!UnregisterClassA` at `0x180011bc3`

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
0x180011b80  push    rbx
0x180011b82  push    rbp
0x180011b83  push    rsi
0x180011b84  push    rdi
0x180011b85  sub     rsp, 28h
0x180011b89  mov     rbp, rdx
0x180011b8c  mov     rbx, rcx
0x180011b8f  test    rcx, rcx
0x180011b92  jz      short loc_180011C06
0x180011b94  cmp     dword ptr [rcx], 0
0x180011b97  jnz     short loc_180011B9D
0x180011b99  xor     eax, eax
0x180011b9b  jmp     short loc_180011C0B
0x180011b9d  cmp     dword ptr [rcx], 48h ; 'H'
0x180011ba0  jnz     short loc_180011C06
0x180011ba2  xor     esi, esi
0x180011ba4  cmp     [rcx+40h], esi
0x180011ba7  jle     short loc_180011BE8
0x180011ba9  test    esi, esi
0x180011bab  js      short loc_180011BD2
0x180011bad  lea     rdi, [rbx+38h]
0x180011bb1  cmp     esi, [rdi+8]
0x180011bb4  jge     short loc_180011BD2
0x180011bb6  mov     rax, [rdi]
0x180011bb9  mov     rdx, rbp; hInstance
0x180011bbc  movsxd  rcx, esi
0x180011bbf  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180011bc3  call    cs:__imp_UnregisterClassA
0x180011bc9  inc     esi
0x180011bcb  cmp     esi, [rbx+40h]
0x180011bce  jl      short loc_180011BA9
0x180011bd0  jmp     short loc_180011BEC
0x180011bd2  xor     r9d, r9d; lpArguments
0x180011bd5  xor     r8d, r8d; nNumberOfArguments
0x180011bd8  mov     ecx, 0C000008Ch; dwExceptionCode
0x180011bdd  lea     edx, [r9+1]; dwExceptionFlags
0x180011be1  call    cs:__imp_RaiseException
0x180011be7  int     3; Trap to Debugger
0x180011be8  lea     rdi, [rcx+38h]
0x180011bec  mov     rcx, rdi
0x180011bef  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180011bf4  lea     rcx, [rbx+8]; lpCriticalSection
0x180011bf8  call    cs:__imp_DeleteCriticalSection
0x180011bfe  mov     dword ptr [rbx], 0
0x180011c04  jmp     short loc_180011B99
0x180011c06  mov     eax, 80070057h
0x180011c0b  add     rsp, 28h
0x180011c0f  pop     rdi
0x180011c10  pop     rsi
0x180011c11  pop     rbp
0x180011c12  pop     rbx
0x180011c13  retn
```
