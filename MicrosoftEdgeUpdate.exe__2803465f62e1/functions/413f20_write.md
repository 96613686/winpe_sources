# __write

- ea: `0x413f20`
- end: `0x414012`
- name: `__write`
- size: `242`
- prototype: `int __cdecl(int FileHandle, const void *Buf, unsigned int MaxCharCount)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x4125c6`

## callees

- `0x40bfc0`
- `0x40de54`
- `0x40ff96`
- `0x40ffa9`
- `0x4110c2`
- `0x4110e5`
- `0x413f20`
- `0x414012`

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
    || FileHandle >= (unsigned int)dword_4183B0
    || (v5 = 56 * (FileHandle & 0x3F), (*(_BYTE *)(dword_4181B0[FileHandle >> 6] + v5 + 40) & 1) == 0) )
  {
    *__doserrno() = 0;
    *_errno() = 9;
    _invalid_parameter_noinfo();
    return -1;
  }
  __acrt_lowio_lock_fh(FileHandle);
  v3 = -1;
  if ( (*(_BYTE *)(dword_4181B0[FileHandle >> 6] + v5 + 40) & 1) != 0 )
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
0x413f20  push    10h
0x413f22  push    offset stru_416C08
0x413f27  call    __SEH_prolog4
0x413f2c  mov     esi, [ebp+FileHandle]
0x413f2f  cmp     esi, 0FFFFFFFEh
0x413f32  jnz     short loc_413F4C
0x413f34  call    ___doserrno
0x413f39  and     dword ptr [eax], 0
0x413f3c  call    __errno
0x413f41  mov     dword ptr [eax], 9
0x413f47  jmp     loc_413FFF
0x413f4c  test    esi, esi
0x413f4e  js      loc_413FE7
0x413f54  cmp     esi, dword_4183B0
0x413f5a  jnb     loc_413FE7
0x413f60  mov     ebx, esi
0x413f62  sar     ebx, 6
0x413f65  mov     eax, esi
0x413f67  and     eax, 3Fh
0x413f6a  imul    ecx, eax, 38h ; '8'
0x413f6d  mov     [ebp+var_20], ecx
0x413f70  mov     eax, dword_4181B0[ebx*4]
0x413f77  test    byte ptr [eax+ecx+28h], 1
0x413f7c  jz      short loc_413FE7
0x413f7e  push    esi
0x413f7f  call    ___acrt_lowio_lock_fh
0x413f84  pop     ecx
0x413f85  or      edi, 0FFFFFFFFh
0x413f88  mov     [ebp+var_1C], edi
0x413f8b  and     [ebp+ms_exc.registration.TryLevel], 0
0x413f8f  mov     eax, dword_4181B0[ebx*4]
0x413f96  mov     ecx, [ebp+var_20]
0x413f99  test    byte ptr [eax+ecx+28h], 1
0x413f9e  jnz     short loc_413FB5
0x413fa0  call    __errno
0x413fa5  mov     dword ptr [eax], 9
0x413fab  call    ___doserrno
0x413fb0  and     dword ptr [eax], 0
0x413fb3  jmp     short loc_413FC9
0x413fb5  push    [ebp+MaxCharCount]; int
0x413fb8  push    [ebp+Buf]; int
0x413fbb  push    esi; FileHandle
0x413fbc  call    __write_nolock
0x413fc1  add     esp, 0Ch
0x413fc4  mov     edi, eax
0x413fc6  mov     [ebp+var_1C], edi
0x413fc9  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x413fd0  call    loc_413FDF
0x413fd5  mov     eax, edi
0x413fd7  jmp     short loc_414002
0x413fd9  mov     esi, [ebp+FileHandle]
0x413fdc  mov     edi, [ebp+var_1C]
0x413fdf  push    esi
0x413fe0  call    ___acrt_lowio_unlock_fh
0x413fe5  pop     ecx
0x413fe6  retn
0x413fe7  call    ___doserrno
0x413fec  and     dword ptr [eax], 0
0x413fef  call    __errno
0x413ff4  mov     dword ptr [eax], 9
0x413ffa  call    __invalid_parameter_noinfo
0x413fff  or      eax, 0FFFFFFFFh
0x414002  mov     ecx, [ebp+ms_exc.registration.Next]
0x414005  mov     large fs:0, ecx
0x41400c  pop     ecx
0x41400d  pop     edi
0x41400e  pop     esi
0x41400f  pop     ebx
0x414010  leave
0x414011  retn
```
