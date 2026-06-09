# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ada0`
- end: `0x18000ae14`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ada0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(
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
    if ( *a2 != 1146277385
      || a2[1] != *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
      || a2[2] != *(_DWORD *)GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4[4];
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
0x18000ada0  push    rbx
0x18000ada2  sub     rsp, 20h
0x18000ada6  xor     ebx, ebx
0x18000ada8  mov     [r8], rbx
0x18000adab  cmp     [rdx], ebx
0x18000adad  jnz     short loc_18000ADE1
0x18000adaf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000adb5  cmp     [rdx+4], eax
0x18000adb8  jnz     short loc_18000AE07
0x18000adba  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000adc0  cmp     [rdx+8], eax
0x18000adc3  jnz     short loc_18000AE07
0x18000adc5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000adcb  cmp     [rdx+0Ch], eax
0x18000adce  jnz     short loc_18000AE07
0x18000add0  mov     [r8], rcx
0x18000add3  mov     rax, [rcx]
0x18000add6  mov     rax, [rax+8]
0x18000adda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000addf  jmp     short loc_18000AE0C
0x18000ade1  cmp     dword ptr [rdx], 4452CE09h
0x18000ade7  jnz     short loc_18000AE07
0x18000ade9  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
0x18000adef  cmp     [rdx+4], eax
0x18000adf2  jnz     short loc_18000AE07
0x18000adf4  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4
0x18000adfa  cmp     [rdx+8], eax
0x18000adfd  jnz     short loc_18000AE07
0x18000adff  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4+4
0x18000ae05  jmp     short loc_18000ADCB
0x18000ae07  mov     ebx, 80004002h
0x18000ae0c  mov     eax, ebx
0x18000ae0e  add     rsp, 20h
0x18000ae12  pop     rbx
0x18000ae13  retn
```
