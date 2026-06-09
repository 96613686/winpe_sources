# common_vsnprintf_s<wchar_t>(unsigned __int64,wchar_t * const,uint,uint,wchar_t const * const,__crt_locale_pointers * const,char * const)

- ea: `0x411764`
- end: `0x411867`
- name: `??$common_vsnprintf_s@_W@@YAH_KQA_WIIQB_WQAU__crt_locale_pointers@@QAD@Z`
- size: `259`
- prototype: `int __cdecl(int, int, _WORD *, unsigned int, unsigned int, int, struct __crt_locale_pointers *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x412f4d`

## callees

- `0x410369`
- `0x410443`
- `0x411764`
- `0x411867`

## pseudocode

```c
int __cdecl common_vsnprintf_s<wchar_t>(
        int a1,
        int a2,
        _WORD *a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        struct __crt_locale_pointers *a7,
        int a8)
{
  int result; // eax
  int *v9; // eax
  int v10; // ebx
  int v11; // [esp+0h] [ebp-4h]

  if ( !a6 )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    return -1;
  }
  if ( a5 )
  {
    if ( !a3 )
    {
LABEL_20:
      *_errno() = 22;
      goto LABEL_21;
    }
  }
  else if ( !a3 )
  {
    if ( !a4 )
      return 0;
    goto LABEL_20;
  }
  if ( !a4 )
    goto LABEL_20;
  v9 = _errno();
  if ( a4 > a5 )
  {
    v10 = *v9;
    result = sub_411867(a1, a2, (int)a3, a5 + 1, a6, a7, a8);
    if ( result == -2 )
    {
      if ( *_errno() == 34 )
        *_errno() = v10;
      return -1;
    }
    goto LABEL_17;
  }
  v11 = *v9;
  result = sub_411867(a1, a2, (int)a3, a4, a6, a7, a8);
  a3[a4 - 1] = 0;
  if ( result != -2 )
  {
LABEL_17:
    if ( result >= 0 )
      return result;
    goto LABEL_18;
  }
  if ( a5 == -1 )
  {
    if ( *_errno() == 34 )
      *_errno() = v11;
    return -1;
  }
LABEL_18:
  *a3 = 0;
  if ( result == -2 )
  {
    *_errno() = 34;
LABEL_21:
    _invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x411764  mov     edi, edi
0x411766  push    ebp
0x411767  mov     ebp, esp
0x411769  push    ecx
0x41176a  cmp     [ebp+arg_14], 0
0x41176e  jnz     short loc_411785
0x411770  call    __errno
0x411775  mov     dword ptr [eax], 16h
0x41177b  call    __invalid_parameter_noinfo
0x411780  or      eax, 0FFFFFFFFh
0x411783  leave
0x411784  retn
0x411785  push    ebx
0x411786  push    esi
0x411787  mov     esi, [ebp+arg_8]
0x41178a  push    edi
0x41178b  mov     edi, [ebp+arg_10]
0x41178e  test    edi, edi
0x411790  jnz     short loc_4117A6
0x411792  test    esi, esi
0x411794  jnz     short loc_4117AE
0x411796  cmp     [ebp+arg_C], esi
0x411799  jnz     loc_41184F
0x41179f  xor     eax, eax
0x4117a1  jmp     loc_411862
0x4117a6  test    esi, esi
0x4117a8  jz      loc_41184F
0x4117ae  mov     ebx, [ebp+arg_C]
0x4117b1  test    ebx, ebx
0x4117b3  jz      loc_41184F
0x4117b9  call    __errno
0x4117be  push    [ebp+arg_1C]; int
0x4117c1  push    [ebp+arg_18]; struct __crt_locale_pointers *
0x4117c4  push    [ebp+arg_14]; int
0x4117c7  cmp     ebx, edi
0x4117c9  jbe     short loc_4117F8
0x4117cb  mov     ebx, [eax]
0x4117cd  lea     eax, [edi+1]
0x4117d0  push    eax; int
0x4117d1  push    esi; int
0x4117d2  push    [ebp+arg_4]; int
0x4117d5  push    [ebp+arg_0]; int
0x4117d8  call    sub_411867
0x4117dd  add     esp, 1Ch
0x4117e0  cmp     eax, 0FFFFFFFEh
0x4117e3  jnz     short loc_411834
0x4117e5  call    __errno
0x4117ea  cmp     dword ptr [eax], 22h ; '"'
0x4117ed  jnz     short loc_41185F
0x4117ef  call    __errno
0x4117f4  mov     [eax], ebx
0x4117f6  jmp     short loc_41185F
0x4117f8  mov     eax, [eax]
0x4117fa  push    ebx; int
0x4117fb  push    esi; int
0x4117fc  push    [ebp+arg_4]; int
0x4117ff  mov     [ebp+var_4], eax
0x411802  push    [ebp+arg_0]; int
0x411805  call    sub_411867
0x41180a  xor     ecx, ecx
0x41180c  add     esp, 1Ch
0x41180f  mov     [esi+ebx*2-2], cx
0x411814  cmp     eax, 0FFFFFFFEh
0x411817  jnz     short loc_411834
0x411819  cmp     edi, 0FFFFFFFFh
0x41181c  jnz     short loc_411838
0x41181e  call    __errno
0x411823  cmp     dword ptr [eax], 22h ; '"'
0x411826  jnz     short loc_41185F
0x411828  call    __errno
0x41182d  mov     ecx, [ebp+var_4]
0x411830  mov     [eax], ecx
0x411832  jmp     short loc_41185F
0x411834  test    eax, eax
0x411836  jns     short loc_411862
0x411838  xor     ecx, ecx
0x41183a  mov     [esi], cx
0x41183d  cmp     eax, 0FFFFFFFEh
0x411840  jnz     short loc_41185F
0x411842  call    __errno
0x411847  mov     dword ptr [eax], 22h ; '"'
0x41184d  jmp     short loc_41185A
0x41184f  call    __errno
0x411854  mov     dword ptr [eax], 16h
0x41185a  call    __invalid_parameter_noinfo
0x41185f  or      eax, 0FFFFFFFFh
0x411862  pop     edi
0x411863  pop     esi
0x411864  pop     ebx
0x411865  leave
0x411866  retn
```
