# dllmain_dispatch(HINSTANCE__ * const,ulong,void * const)

- ea: `0x10010920`
- end: `0x10010a26`
- name: `?dllmain_dispatch@@YAHQAUHINSTANCE__@@KQAX@Z`
- size: `262`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, void *const lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x10010a51`

## callees

- `0x10007086`
- `0x10010731`
- `0x10010920`
- `0x10010a26`
- `0x10010dd6`
- `0x10011180`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, void *const lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_100349C0 <= 0 )
    return 0;
  if ( fdwReason != 1 && fdwReason != 2 )
  {
    v4 = lpvReserved;
LABEL_9:
    v6 = DllMain(hinstDLL, fdwReason, v4);
    v5 = v6;
    if ( fdwReason == 1 && !v6 )
    {
      DllMain(hinstDLL, 0, v4);
      dllmain_crt_dispatch(hinstDLL, 0, v4);
      dllmain_raw(hinstDLL, 0, v4);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, v4);
      if ( v5 )
        return dllmain_raw(hinstDLL, fdwReason, v4);
    }
    return v5;
  }
  v4 = lpvReserved;
  v5 = dllmain_raw(hinstDLL, fdwReason, lpvReserved);
  if ( v5 )
  {
    v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
    if ( v5 )
      goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x10010920  push    0Ch
0x10010922  push    offset stru_10030F80
0x10010927  call    __SEH_prolog4
0x1001092c  mov     edi, [ebp+fdwReason]
0x1001092f  test    edi, edi
0x10010931  jnz     short loc_10010942
0x10010933  cmp     dword_100349C0, edi
0x10010939  jg      short loc_10010942
0x1001093b  xor     eax, eax
0x1001093d  jmp     loc_10010A16
0x10010942  and     [ebp+ms_exc.registration.TryLevel], 0
0x10010946  cmp     edi, 1
0x10010949  jz      short loc_10010955
0x1001094b  cmp     edi, 2
0x1001094e  jz      short loc_10010955
0x10010950  mov     ebx, [ebp+lpvReserved]
0x10010953  jmp     short loc_10010986
0x10010955  mov     ebx, [ebp+lpvReserved]
0x10010958  push    ebx; void *
0x10010959  push    edi; unsigned int
0x1001095a  push    [ebp+hinstDLL]; HINSTANCE
0x1001095d  call    ?dllmain_raw@@YGHQAUHINSTANCE__@@KQAX@Z
0x10010962  mov     esi, eax
0x10010964  mov     [ebp+var_1C], esi
0x10010967  test    esi, esi
0x10010969  jz      loc_10010A0D
0x1001096f  push    ebx; void *
0x10010970  push    edi; unsigned int
0x10010971  push    [ebp+hinstDLL]; HINSTANCE
0x10010974  call    ?dllmain_crt_dispatch@@YGHQAUHINSTANCE__@@KQAX@Z
0x10010979  mov     esi, eax
0x1001097b  mov     [ebp+var_1C], esi
0x1001097e  test    esi, esi
0x10010980  jz      loc_10010A0D
0x10010986  push    ebx; lpvReserved
0x10010987  push    edi; fdwReason
0x10010988  push    [ebp+hinstDLL]; hinstDLL
0x1001098b  call    _DllMain@12
0x10010990  mov     esi, eax
0x10010992  mov     [ebp+var_1C], esi
0x10010995  cmp     edi, 1
0x10010998  jnz     short loc_100109BC
0x1001099a  test    esi, esi
0x1001099c  jnz     short loc_100109BC
0x1001099e  push    ebx; lpvReserved
0x1001099f  push    eax; fdwReason
0x100109a0  push    [ebp+hinstDLL]; hinstDLL
0x100109a3  call    _DllMain@12
0x100109a8  push    ebx; void *
0x100109a9  push    esi; unsigned int
0x100109aa  push    [ebp+hinstDLL]; HINSTANCE
0x100109ad  call    ?dllmain_crt_dispatch@@YGHQAUHINSTANCE__@@KQAX@Z
0x100109b2  push    ebx; void *
0x100109b3  push    esi; unsigned int
0x100109b4  push    [ebp+hinstDLL]; HINSTANCE
0x100109b7  call    ?dllmain_raw@@YGHQAUHINSTANCE__@@KQAX@Z
0x100109bc  test    edi, edi
0x100109be  jz      short loc_100109C5
0x100109c0  cmp     edi, 3
0x100109c3  jnz     short loc_10010A0D
0x100109c5  push    ebx; void *
0x100109c6  push    edi; unsigned int
0x100109c7  push    [ebp+hinstDLL]; HINSTANCE
0x100109ca  call    ?dllmain_crt_dispatch@@YGHQAUHINSTANCE__@@KQAX@Z
0x100109cf  mov     esi, eax
0x100109d1  mov     [ebp+var_1C], esi
0x100109d4  test    esi, esi
0x100109d6  jz      short loc_10010A0D
0x100109d8  push    ebx; void *
0x100109d9  push    edi; unsigned int
0x100109da  push    [ebp+hinstDLL]; HINSTANCE
0x100109dd  call    ?dllmain_raw@@YGHQAUHINSTANCE__@@KQAX@Z
0x100109e2  mov     esi, eax
0x100109e4  jmp     short loc_10010A0A
0x100109e6  mov     ecx, [ebp+ms_exc.exc_ptr]
0x100109e9  mov     eax, [ecx]
0x100109eb  push    ecx; ExceptionPtr
0x100109ec  push    dword ptr [eax]; ExceptionNum
0x100109ee  push    offset ?dllmain_crt_dispatch@@YGHQAUHINSTANCE__@@KQAX@Z; int
0x100109f3  push    [ebp+lpvReserved]; int
0x100109f6  push    [ebp+fdwReason]; int
0x100109f9  push    [ebp+hinstDLL]; int
0x100109fc  call    ___scrt_dllmain_exception_filter
0x10010a01  add     esp, 18h
0x10010a04  retn
0x10010a05  mov     esp, [ebp+ms_exc.old_esp]
0x10010a08  xor     esi, esi
0x10010a0a  mov     [ebp+var_1C], esi
0x10010a0d  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10010a14  mov     eax, esi
0x10010a16  mov     ecx, [ebp+ms_exc.registration.Next]
0x10010a19  mov     large fs:0, ecx
0x10010a20  pop     ecx
0x10010a21  pop     edi
0x10010a22  pop     esi
0x10010a23  pop     ebx
0x10010a24  leave
0x10010a25  retn
```
