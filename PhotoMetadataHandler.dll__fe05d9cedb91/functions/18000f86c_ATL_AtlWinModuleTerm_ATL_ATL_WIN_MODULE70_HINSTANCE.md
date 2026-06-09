# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000f86c`
- end: `0x18000f900`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f840`

## callees

- `0x18000f86c`
- `0x18000f908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f8f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f8f2`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18000f8d4`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18000f8d4`

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
            RaiseException(0xC000008C, 1u, 0, 0);
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
0x18000f86c  push    rbx
0x18000f86e  push    rbp
0x18000f86f  push    rsi
0x18000f870  push    rdi
0x18000f871  sub     rsp, 28h
0x18000f875  mov     rbp, rdx
0x18000f878  mov     rbx, rcx
0x18000f87b  test    rcx, rcx
0x18000f87e  jz      short loc_18000F8F9
0x18000f880  cmp     dword ptr [rcx], 0
0x18000f883  jnz     short loc_18000F890
0x18000f885  xor     eax, eax
0x18000f887  add     rsp, 28h
0x18000f88b  pop     rdi
0x18000f88c  pop     rsi
0x18000f88d  pop     rbp
0x18000f88e  pop     rbx
0x18000f88f  retn
0x18000f890  cmp     dword ptr [rcx], 48h ; 'H'
0x18000f893  jnz     short loc_18000F8F9
0x18000f895  xor     esi, esi
0x18000f897  cmp     [rcx+40h], esi
0x18000f89a  jg      short loc_18000F8BA
0x18000f89c  lea     rdi, [rcx+38h]
0x18000f8a0  mov     rcx, rdi
0x18000f8a3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000f8a8  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f8ac  call    cs:__imp_DeleteCriticalSection
0x18000f8b2  mov     dword ptr [rbx], 0
0x18000f8b8  jmp     short loc_18000F885
0x18000f8ba  test    esi, esi
0x18000f8bc  js      short loc_18000F8E3
0x18000f8be  lea     rdi, [rbx+38h]
0x18000f8c2  cmp     esi, [rdi+8]
0x18000f8c5  jge     short loc_18000F8E3
0x18000f8c7  mov     rax, [rdi]
0x18000f8ca  mov     rdx, rbp; hInstance
0x18000f8cd  movsxd  rcx, esi
0x18000f8d0  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000f8d4  call    cs:__imp_UnregisterClassA
0x18000f8da  inc     esi
0x18000f8dc  cmp     esi, [rbx+40h]
0x18000f8df  jl      short loc_18000F8BA
0x18000f8e1  jmp     short loc_18000F8A0
0x18000f8e3  xor     r9d, r9d; lpArguments
0x18000f8e6  xor     r8d, r8d; nNumberOfArguments
0x18000f8e9  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000f8ee  lea     edx, [r9+1]; dwExceptionFlags
0x18000f8f2  call    cs:__imp_RaiseException
0x18000f8f8  int     3; Trap to Debugger
0x18000f8f9  mov     eax, 80070057h
0x18000f8fe  jmp     short loc_18000F887
```
