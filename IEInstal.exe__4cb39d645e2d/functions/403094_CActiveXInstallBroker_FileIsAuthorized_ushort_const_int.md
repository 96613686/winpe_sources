# CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)

- ea: `0x403094`
- end: `0x4030ef`
- name: `?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z`
- size: `91`
- prototype: `int __thiscall(CActiveXInstallBroker *__hidden this, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x40304d`
- `0x403d84`
- `0x403ffd`
- `0x404214`
- `0x4044ae`
- `0x40494e`

## callees

- `0x403094`
- `0x406a93`
- `0x406f2f`
- `0x4075cd`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x4030da`
- `ole32!CoTaskMemFree` at `0x4030da`

## pseudocode

```c
int __thiscall CActiveXInstallBroker::FileIsAuthorized(CActiveXInstallBroker *this, const unsigned __int16 *a2, int a3)
{
  int v3; // edi
  int v4; // esi
  const unsigned __int16 *v6; // [esp+0h] [ebp-Ch]
  const unsigned __int16 *v7; // [esp+0h] [ebp-Ch]
  const char *v8; // [esp+0h] [ebp-Ch]
  int v9; // [esp+4h] [ebp-8h]
  char **v10; // [esp+4h] [ebp-8h]
  struct sFNAME *v11; // [esp+4h] [ebp-8h]
  LPVOID pv; // [esp+8h] [ebp-4h] BYREF

  v3 = -2147024891;
  if ( !IsFileAtIntegrityLevel(v6, v9) )
  {
    pv = 0;
    if ( WSZtoSZ((unsigned int)&pv, v7, v10) >= 0 )
    {
      v4 = IsInFileListA(v8, v11);
      CoTaskMemFree(pv);
      if ( v4 )
        return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x403094  mov     edi, edi
0x403096  push    ebp
0x403097  mov     ebp, esp
0x403099  push    ecx
0x40309a  push    esi; struct sFNAME *
0x40309b  mov     esi, ecx
0x40309d  mov     ecx, [ebp+arg_0]
0x4030a0  push    edi; char *
0x4030a1  mov     edi, 80070005h
0x4030a6  call    ?IsFileAtIntegrityLevel@@YGJPBGH@Z; IsFileAtIntegrityLevel(ushort const *,int)
0x4030ab  test    eax, eax
0x4030ad  js      short loc_4030E7
0x4030af  jnz     short loc_4030E7
0x4030b1  mov     edx, [ebp+arg_0]
0x4030b4  lea     eax, [ebp+pv]
0x4030b7  mov     esi, [esi+4Ch]
0x4030ba  push    eax; unsigned int
0x4030bb  mov     [ebp+pv], 0
0x4030c2  call    ?WSZtoSZ@@YGJIPBGPAPAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x4030c7  test    eax, eax
0x4030c9  js      short loc_4030E7
0x4030cb  mov     ecx, [ebp+pv]
0x4030ce  mov     edx, esi
0x4030d0  call    ?IsInFileListA@@YGHPBDPAUsFNAME@@@Z; IsInFileListA(char const *,sFNAME *)
0x4030d5  push    [ebp+pv]; pv
0x4030d8  mov     esi, eax
0x4030da  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x4030e0  xor     eax, eax
0x4030e2  test    esi, esi
0x4030e4  cmovnz  edi, eax
0x4030e7  mov     eax, edi
0x4030e9  pop     edi
0x4030ea  pop     esi
0x4030eb  leave
0x4030ec  retn    8
```
