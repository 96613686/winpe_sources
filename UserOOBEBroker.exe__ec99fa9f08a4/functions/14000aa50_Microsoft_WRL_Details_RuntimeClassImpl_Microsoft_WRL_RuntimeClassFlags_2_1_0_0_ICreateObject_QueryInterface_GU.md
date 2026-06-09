# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000aa50`
- end: `0x14000aac4`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008d40`

## callees

- `0x14000aa50`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != 1964120402
      || a2[1] != *(_DWORD *)&GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data2
      || a2[2] != *(_DWORD *)GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x14000aa50  push    rbx
0x14000aa52  sub     rsp, 20h
0x14000aa56  xor     ebx, ebx
0x14000aa58  mov     [r8], rbx
0x14000aa5b  cmp     [rdx], ebx
0x14000aa5d  jnz     short loc_14000AA91
0x14000aa5f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000aa65  cmp     [rdx+4], eax
0x14000aa68  jnz     short loc_14000AAB7
0x14000aa6a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000aa70  cmp     [rdx+8], eax
0x14000aa73  jnz     short loc_14000AAB7
0x14000aa75  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000aa7b  cmp     [rdx+0Ch], eax
0x14000aa7e  jnz     short loc_14000AAB7
0x14000aa80  mov     [r8], rcx
0x14000aa83  mov     rax, [rcx]
0x14000aa86  mov     rax, [rax+8]
0x14000aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa8f  jmp     short loc_14000AABC
0x14000aa91  cmp     dword ptr [rdx], 75121952h
0x14000aa97  jnz     short loc_14000AAB7
0x14000aa99  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data2
0x14000aa9f  cmp     [rdx+4], eax
0x14000aaa2  jnz     short loc_14000AAB7
0x14000aaa4  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4
0x14000aaaa  cmp     [rdx+8], eax
0x14000aaad  jnz     short loc_14000AAB7
0x14000aaaf  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4+4
0x14000aab5  jmp     short loc_14000AA7B
0x14000aab7  mov     ebx, 80004002h
0x14000aabc  mov     eax, ebx
0x14000aabe  add     rsp, 20h
0x14000aac2  pop     rbx
0x14000aac3  retn
```
