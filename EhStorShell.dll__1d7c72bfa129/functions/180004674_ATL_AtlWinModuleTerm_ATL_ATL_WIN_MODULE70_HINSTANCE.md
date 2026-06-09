# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180004674`
- end: `0x180004708`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c18`

## callees

- `0x180004674`
- `0x180005c44`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800046d5`
- `KERNEL32!RaiseException` at `0x1800046d5`
- `KERNEL32!DeleteCriticalSection` at `0x1800046ec`
- `KERNEL32!DeleteCriticalSection` at `0x1800046ec`
- `USER32!UnregisterClassA` at `0x1800046b7`
- `USER32!UnregisterClassA` at `0x1800046b7`

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
0x180004674  push    rbx
0x180004676  push    rbp
0x180004677  push    rsi
0x180004678  push    rdi
0x180004679  sub     rsp, 28h
0x18000467d  mov     rbp, rdx
0x180004680  mov     rbx, rcx
0x180004683  test    rcx, rcx
0x180004686  jz      short loc_1800046FA
0x180004688  cmp     dword ptr [rcx], 0
0x18000468b  jnz     short loc_180004691
0x18000468d  xor     eax, eax
0x18000468f  jmp     short loc_1800046FF
0x180004691  cmp     dword ptr [rcx], 48h ; 'H'
0x180004694  jnz     short loc_1800046FA
0x180004696  xor     esi, esi
0x180004698  cmp     [rcx+40h], esi
0x18000469b  jle     short loc_1800046DC
0x18000469d  test    esi, esi
0x18000469f  js      short loc_1800046C6
0x1800046a1  lea     rdi, [rbx+38h]
0x1800046a5  cmp     esi, [rdi+8]
0x1800046a8  jge     short loc_1800046C6
0x1800046aa  mov     rax, [rdi]
0x1800046ad  mov     rdx, rbp; hInstance
0x1800046b0  movsxd  rcx, esi
0x1800046b3  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800046b7  call    cs:__imp_UnregisterClassA
0x1800046bd  inc     esi
0x1800046bf  cmp     esi, [rbx+40h]
0x1800046c2  jl      short loc_18000469D
0x1800046c4  jmp     short loc_1800046E0
0x1800046c6  xor     r9d, r9d; lpArguments
0x1800046c9  xor     r8d, r8d; nNumberOfArguments
0x1800046cc  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800046d1  lea     edx, [r9+1]; dwExceptionFlags
0x1800046d5  call    cs:__imp_RaiseException
0x1800046db  int     3; Trap to Debugger
0x1800046dc  lea     rdi, [rcx+38h]
0x1800046e0  mov     rcx, rdi
0x1800046e3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800046e8  lea     rcx, [rbx+8]; lpCriticalSection
0x1800046ec  call    cs:__imp_DeleteCriticalSection
0x1800046f2  mov     dword ptr [rbx], 0
0x1800046f8  jmp     short loc_18000468D
0x1800046fa  mov     eax, 80070057h
0x1800046ff  add     rsp, 28h
0x180004703  pop     rdi
0x180004704  pop     rsi
0x180004705  pop     rbp
0x180004706  pop     rbx
0x180004707  retn
```
