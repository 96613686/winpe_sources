# __acrt_SetThreadStackGuarantee(x)

- ea: `0x41515e`
- end: `0x415199`
- name: `___acrt_SetThreadStackGuarantee@4`
- size: `59`
- prototype: `int __stdcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x41fb14`

## callees

- `0x402330`
- `0x414ec2`
- `0x41515e`

## string_xrefs

- `0x415164`: `SetThreadStackGuarantee`
- `0x41516e`: `SetThreadStackGuarantee`

## pseudocode

```c
int __stdcall __acrt_SetThreadStackGuarantee(int a1)
{
  FARPROC function; // eax

  function = try_get_function(32, "SetThreadStackGuarantee", dword_424358, "SetThreadStackGuarantee");
  if ( function )
    return ((int (__thiscall *)(FARPROC, int))function)(function, a1);
  else
    return 0;
}

```

## disassembly

```asm
0x41515e  mov     edi, edi
0x415160  push    ebp
0x415161  mov     ebp, esp
0x415163  push    esi
0x415164  push    offset aSetthreadstack
0x415169  push    offset dword_424358
0x41516e  push    offset aSetthreadstack
0x415173  push    20h ; ' '
0x415175  call    ?try_get_function@@YAPAXW4function_id@?A0x391cf84c@@QBDQBW4module_id@2@2@Z
0x41517a  mov     esi, eax
0x41517c  add     esp, 10h
0x41517f  test    esi, esi
0x415181  jz      short loc_415192
0x415183  push    [ebp+arg_0]
0x415186  mov     ecx, esi
0x415188  call    ds:___guard_check_icall_fptr
0x41518e  call    esi
0x415190  jmp     short loc_415194
0x415192  xor     eax, eax
0x415194  pop     esi
0x415195  pop     ebp
0x415196  retn    4
```
