# common_vsprintf_s<wchar_t>(unsigned __int64,wchar_t * const,uint,wchar_t const * const,__crt_locale_pointers * const,char * const)

- ea: `0x40c668`
- end: `0x40c6e2`
- name: `??$common_vsprintf_s@_W@@YAH_KQA_WIQB_WQAU__crt_locale_pointers@@QAD@Z`
- size: `122`
- prototype: `int __cdecl(int, int, _WORD *, int, int, struct __crt_locale_pointers *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x40daf1`

## callees

- `0x40c35a`
- `0x40c668`
- `0x40ec26`
- `0x40ece3`

## pseudocode

```c
int __cdecl common_vsprintf_s<wchar_t>(
        int a1,
        int a2,
        _WORD *a3,
        int a4,
        int a5,
        struct __crt_locale_pointers *a6,
        int a7)
{
  int result; // eax

  if ( !a5 )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    return -1;
  }
  if ( !a3 || !a4 )
  {
    *_errno() = 22;
    goto LABEL_10;
  }
  result = sub_40C35A(a1, a2, (int)a3, a4, a5, a6, a7);
  if ( result < 0 )
    *a3 = 0;
  if ( result == -2 )
  {
    *_errno() = 34;
LABEL_10:
    _invalid_parameter_noinfo();
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x40c668  mov     edi, edi
0x40c66a  push    ebp
0x40c66b  mov     ebp, esp
0x40c66d  cmp     [ebp+arg_10], 0
0x40c671  jnz     short loc_40C688
0x40c673  call    __errno
0x40c678  mov     dword ptr [eax], 16h
0x40c67e  call    __invalid_parameter_noinfo
0x40c683  or      eax, 0FFFFFFFFh
0x40c686  pop     ebp
0x40c687  retn
0x40c688  push    esi
0x40c689  mov     esi, [ebp+arg_8]
0x40c68c  test    esi, esi
0x40c68e  jz      short loc_40C6CC
0x40c690  cmp     [ebp+arg_C], 0
0x40c694  jbe     short loc_40C6CC
0x40c696  push    [ebp+arg_18]; int
0x40c699  push    [ebp+arg_14]; struct __crt_locale_pointers *
0x40c69c  push    [ebp+arg_10]; int
0x40c69f  push    [ebp+arg_C]; int
0x40c6a2  push    esi; int
0x40c6a3  push    [ebp+arg_4]; int
0x40c6a6  push    [ebp+arg_0]; int
0x40c6a9  call    sub_40C35A
0x40c6ae  add     esp, 1Ch
0x40c6b1  test    eax, eax
0x40c6b3  jns     short loc_40C6BA
0x40c6b5  xor     ecx, ecx
0x40c6b7  mov     [esi], cx
0x40c6ba  cmp     eax, 0FFFFFFFEh
0x40c6bd  jnz     short loc_40C6DF
0x40c6bf  call    __errno
0x40c6c4  mov     dword ptr [eax], 22h ; '"'
0x40c6ca  jmp     short loc_40C6D7
0x40c6cc  call    __errno
0x40c6d1  mov     dword ptr [eax], 16h
0x40c6d7  call    __invalid_parameter_noinfo
0x40c6dc  or      eax, 0FFFFFFFFh
0x40c6df  pop     esi
0x40c6e0  pop     ebp
0x40c6e1  retn
```
