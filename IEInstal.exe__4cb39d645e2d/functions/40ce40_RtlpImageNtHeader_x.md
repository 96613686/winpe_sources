# RtlpImageNtHeader(x)

- ea: `0x40ce40`
- end: `0x40ceae`
- name: `_RtlpImageNtHeader@4`
- size: `110`
- prototype: `int __stdcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x40ceb4`

## callees

- `0x40ce40`
- `0x40d13c`

## pseudocode

```c
int __stdcall RtlpImageNtHeader(int a1)
{
  int result; // eax
  unsigned int v2; // edx

  result = 0;
  if ( a1 )
  {
    if ( a1 != -1 && *(_WORD *)a1 == 23117 )
    {
      v2 = *(_DWORD *)(a1 + 60);
      if ( v2 < 0x10000000 )
      {
        result = v2 + a1;
        if ( *(_DWORD *)(v2 + a1) != 17744 )
          return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x40ce40  push    0Ch
0x40ce42  push    offset stru_40EC50
0x40ce47  call    __SEH_prolog4
0x40ce4c  xor     eax, eax
0x40ce4e  mov     ecx, [ebp+arg_0]
0x40ce51  test    ecx, ecx
0x40ce53  jz      short loc_40CE9C
0x40ce55  cmp     ecx, 0FFFFFFFFh
0x40ce58  jz      short loc_40CE9C
0x40ce5a  mov     [ebp+ms_exc.registration.TryLevel], eax
0x40ce5d  mov     edx, 5A4Dh
0x40ce62  cmp     [ecx], dx
0x40ce65  jnz     short loc_40CE95
0x40ce67  mov     edx, [ecx+3Ch]
0x40ce6a  test    edx, edx
0x40ce6c  js      short loc_40CE95
0x40ce6e  cmp     edx, 10000000h
0x40ce74  jnb     short loc_40CE95
0x40ce76  lea     eax, [edx+ecx]
0x40ce79  mov     [ebp+var_1C], eax
0x40ce7c  xor     ecx, ecx
0x40ce7e  cmp     dword ptr [eax], 4550h
0x40ce84  cmovnz  eax, ecx
0x40ce87  jmp     short loc_40CE92
0x40ce89  xor     eax, eax
0x40ce8b  inc     eax
0x40ce8c  retn
0x40ce8d  mov     esp, [ebp+ms_exc.old_esp]
0x40ce90  xor     eax, eax
0x40ce92  mov     [ebp+var_1C], eax
0x40ce95  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40ce9c  mov     ecx, [ebp+ms_exc.registration.Next]
0x40ce9f  mov     large fs:0, ecx
0x40cea6  pop     ecx
0x40cea7  pop     edi
0x40cea8  pop     esi
0x40cea9  pop     ebx
0x40ceaa  leave
0x40ceab  retn    4
```
