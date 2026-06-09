# CActiveXInstallBroker::CallSystemInstallerVerifyFile(ushort *,ushort * *)

- ea: `0x40301a`
- end: `0x403047`
- name: `?CallSystemInstallerVerifyFile@CActiveXInstallBroker@@AAEJPAGPAPAG@Z`
- size: `45`
- prototype: `int __thiscall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40373b`

## callees

- `0x40301a`
- `0x40d1d0`

## pseudocode

```c
int __thiscall CActiveXInstallBroker::CallSystemInstallerVerifyFile(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v3; // ecx
  int result; // eax

  v3 = *((_DWORD *)this + 23);
  result = -2147024891;
  if ( v3 )
    return (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *, unsigned __int16 **))(*(_DWORD *)v3 + 12))(
             *(_DWORD *)(*(_DWORD *)v3 + 12),
             v3,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x40301a  mov     edi, edi
0x40301c  push    ebp
0x40301d  mov     ebp, esp
0x40301f  mov     ecx, [ecx+5Ch]
0x403022  mov     eax, 80070005h
0x403027  test    ecx, ecx
0x403029  jz      short loc_403043
0x40302b  mov     eax, [ecx]
0x40302d  push    esi
0x40302e  push    [ebp+arg_4]
0x403031  push    [ebp+arg_0]
0x403034  mov     esi, [eax+0Ch]
0x403037  push    ecx
0x403038  mov     ecx, esi
0x40303a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x403040  call    esi
0x403042  pop     esi
0x403043  pop     ebp
0x403044  retn    8
```
