# __write

- ea: `0x418f45`
- end: `0x419037`
- name: `__write`
- size: `242`
- prototype: `int __cdecl(int FileHandle, const void *Buf, unsigned int MaxCharCount)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x415a50`

## callees

- `0x40dc70`
- `0x410369`
- `0x410430`
- `0x410443`
- `0x415e78`
- `0x415e9b`
- `0x418f45`
- `0x419037`

## pseudocode

```c
int __cdecl _write(int FileHandle, const void *Buf, unsigned int MaxCharCount)
{
  int v3; // edi
  int v5; // [esp+10h] [ebp-20h]

  if ( FileHandle == -2 )
  {
    *__doserrno() = 0;
    *_errno() = 9;
    return -1;
  }
  if ( FileHandle < 0
    || FileHandle >= (unsigned int)dword_43E788
    || (v5 = 56 * (FileHandle & 0x3F), (*(_BYTE *)(dword_43E588[FileHandle >> 6] + v5 + 40) & 1) == 0) )
  {
    *__doserrno() = 0;
    *_errno() = 9;
    _invalid_parameter_noinfo();
    return -1;
  }
  __acrt_lowio_lock_fh(FileHandle);
  v3 = -1;
  if ( (*(_BYTE *)(dword_43E588[FileHandle >> 6] + v5 + 40) & 1) != 0 )
  {
    v3 = _write_nolock(FileHandle, (int)Buf, MaxCharCount);
  }
  else
  {
    *_errno() = 9;
    *__doserrno() = 0;
  }
  __acrt_lowio_unlock_fh(FileHandle);
  return v3;
}

```

## disassembly

```asm
0x418f45  push    10h
0x418f47  push    offset stru_43B828
0x418f4c  call    __SEH_prolog4
0x418f51  mov     esi, [ebp+FileHandle]
0x418f54  cmp     esi, 0FFFFFFFEh
0x418f57  jnz     short loc_418F71
0x418f59  call    ___doserrno
0x418f5e  and     dword ptr [eax], 0
0x418f61  call    __errno
0x418f66  mov     dword ptr [eax], 9
0x418f6c  jmp     loc_419024
0x418f71  test    esi, esi
0x418f73  js      loc_41900C
0x418f79  cmp     esi, dword_43E788
0x418f7f  jnb     loc_41900C
0x418f85  mov     ebx, esi
0x418f87  sar     ebx, 6
0x418f8a  mov     eax, esi
0x418f8c  and     eax, 3Fh
0x418f8f  imul    ecx, eax, 38h ; '8'
0x418f92  mov     [ebp+var_20], ecx
0x418f95  mov     eax, dword_43E588[ebx*4]
0x418f9c  test    byte ptr [eax+ecx+28h], 1
0x418fa1  jz      short loc_41900C
0x418fa3  push    esi
0x418fa4  call    ___acrt_lowio_lock_fh
0x418fa9  pop     ecx
0x418faa  or      edi, 0FFFFFFFFh
0x418fad  mov     [ebp+var_1C], edi
0x418fb0  and     [ebp+ms_exc.registration.TryLevel], 0
0x418fb4  mov     eax, dword_43E588[ebx*4]
0x418fbb  mov     ecx, [ebp+var_20]
0x418fbe  test    byte ptr [eax+ecx+28h], 1
0x418fc3  jnz     short loc_418FDA
0x418fc5  call    __errno
0x418fca  mov     dword ptr [eax], 9
0x418fd0  call    ___doserrno
0x418fd5  and     dword ptr [eax], 0
0x418fd8  jmp     short loc_418FEE
0x418fda  push    [ebp+MaxCharCount]; int
0x418fdd  push    [ebp+Buf]; int
0x418fe0  push    esi; FileHandle
0x418fe1  call    __write_nolock
0x418fe6  add     esp, 0Ch
0x418fe9  mov     edi, eax
0x418feb  mov     [ebp+var_1C], edi
0x418fee  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x418ff5  call    loc_419004
0x418ffa  mov     eax, edi
0x418ffc  jmp     short loc_419027
0x418ffe  mov     esi, [ebp+FileHandle]
0x419001  mov     edi, [ebp+var_1C]
0x419004  push    esi
0x419005  call    ___acrt_lowio_unlock_fh
0x41900a  pop     ecx
0x41900b  retn
0x41900c  call    ___doserrno
0x419011  and     dword ptr [eax], 0
0x419014  call    __errno
0x419019  mov     dword ptr [eax], 9
0x41901f  call    __invalid_parameter_noinfo
0x419024  or      eax, 0FFFFFFFFh
0x419027  mov     ecx, [ebp+ms_exc.registration.Next]
0x41902a  mov     large fs:0, ecx
0x419031  pop     ecx
0x419032  pop     edi
0x419033  pop     esi
0x419034  pop     ebx
0x419035  leave
0x419036  retn
```
