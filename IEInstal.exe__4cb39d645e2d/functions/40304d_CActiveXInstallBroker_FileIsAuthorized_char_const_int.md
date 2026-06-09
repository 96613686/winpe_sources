# CActiveXInstallBroker::FileIsAuthorized(char const *,int)

- ea: `0x40304d`
- end: `0x40308e`
- name: `?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBDH@Z`
- size: `65`
- prototype: `int __thiscall(CActiveXInstallBroker *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x405628`
- `0x40576c`

## callees

- `0x40304d`
- `0x403094`
- `0x406b37`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x403080`
- `ole32!CoTaskMemFree` at `0x403080`

## pseudocode

```c
int __thiscall CActiveXInstallBroker::FileIsAuthorized(CActiveXInstallBroker *this, const char *a2, int a3)
{
  int v4; // ecx
  int IsAuthorized; // esi
  const char *v7; // [esp+0h] [ebp-Ch]
  unsigned __int16 **v8; // [esp+4h] [ebp-8h]
  LPVOID pv; // [esp+8h] [ebp-4h] BYREF

  pv = 0;
  IsAuthorized = SZtoWSZ((unsigned int)&pv, v7, v8);
  if ( IsAuthorized >= 0 )
  {
    IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, (const unsigned __int16 *)pv, v4);
    CoTaskMemFree(pv);
  }
  return IsAuthorized;
}

```

## disassembly

```asm
0x40304d  mov     edi, edi
0x40304f  push    ebp
0x403050  mov     ebp, esp
0x403052  push    ecx
0x403053  mov     edx, [ebp+arg_0]
0x403056  lea     eax, [ebp+pv]
0x403059  push    esi; unsigned __int16 **
0x40305a  push    edi; char *
0x40305b  push    eax; unsigned int
0x40305c  mov     edi, ecx
0x40305e  mov     [ebp+pv], 0
0x403065  call    ?SZtoWSZ@@YGJIPBDPAPAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x40306a  mov     esi, eax
0x40306c  test    esi, esi
0x40306e  js      short loc_403086
0x403070  push    ecx; int
0x403071  push    [ebp+pv]; unsigned __int16 *
0x403074  mov     ecx, edi; this
0x403076  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x40307b  push    [ebp+pv]; pv
0x40307e  mov     esi, eax
0x403080  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x403086  pop     edi
0x403087  mov     eax, esi
0x403089  pop     esi
0x40308a  leave
0x40308b  retn    8
```
