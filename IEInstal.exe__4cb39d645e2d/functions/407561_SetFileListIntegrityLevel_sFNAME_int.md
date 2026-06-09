# SetFileListIntegrityLevel(sFNAME *,int)

- ea: `0x407561`
- end: `0x4075c7`
- name: `?SetFileListIntegrityLevel@@YGJPAUsFNAME@@H@Z`
- size: `102`
- prototype: `int __usercall@<eax>(_DWORD *@<ecx>, const char *@<edi>)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x405628`
- `0x40576c`

## callees

- `0x406b37`
- `0x4074cf`
- `0x407561`
- `0x4075cd`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x4075a7`
- `ole32!CoTaskMemFree` at `0x4075a7`

## pseudocode

```c
int __usercall SetFileListIntegrityLevel@<eax>(_DWORD *a1@<ecx>, const char *a2@<edi>)
{
  _DWORD *v2; // esi
  int result; // eax
  int v4; // edi
  const char *v5; // [esp-4h] [ebp-Ch]
  unsigned __int16 **v6; // [esp+0h] [ebp-8h]
  LPVOID pv; // [esp+4h] [ebp-4h] BYREF

  v2 = a1;
  result = 0;
  if ( a1 )
  {
    v5 = a2;
    do
    {
      if ( *v2 )
      {
        pv = 0;
        result = SZtoWSZ((unsigned int)&pv, v5, v6);
        if ( result < 0 )
          return result;
        v4 = IsFileAtIntegrityLevel((const WCHAR *)pv);
        if ( v4 == 1 )
          v4 = SetFileIntegrityLevelByNameW((const WCHAR *)pv);
        CoTaskMemFree(pv);
        result = 0;
        if ( v4 != -2147024894 )
          result = v4;
        if ( result < 0 )
          return result;
        v2 = (_DWORD *)v2[1];
      }
    }
    while ( v2 );
  }
  return result;
}

```

## disassembly

```asm
0x407561  mov     edi, edi
0x407563  push    ebp
0x407564  mov     ebp, esp
0x407566  push    ecx
0x407567  push    esi; int
0x407568  mov     esi, ecx
0x40756a  xor     eax, eax
0x40756c  test    esi, esi
0x40756e  jz      short loc_4075C4
0x407570  push    edi; unsigned __int16 *
0x407571  mov     edx, [esi]
0x407573  test    edx, edx
0x407575  jz      short loc_4075BF
0x407577  lea     eax, [ebp+pv]
0x40757a  mov     [ebp+pv], 0
0x407581  push    eax; unsigned int
0x407582  call    ?SZtoWSZ@@YGJIPBDPAPAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x407587  test    eax, eax
0x407589  js      short loc_4075C3
0x40758b  mov     ecx, [ebp+pv]
0x40758e  call    ?IsFileAtIntegrityLevel@@YGJPBGH@Z; IsFileAtIntegrityLevel(ushort const *,int)
0x407593  mov     edi, eax
0x407595  cmp     edi, 1
0x407598  jnz     short loc_4075A4
0x40759a  mov     ecx, [ebp+pv]
0x40759d  call    ?SetFileIntegrityLevelByNameW@@YGJPBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x4075a2  mov     edi, eax
0x4075a4  push    [ebp+pv]; pv
0x4075a7  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x4075ad  xor     eax, eax
0x4075af  cmp     edi, 80070002h
0x4075b5  cmovnz  eax, edi
0x4075b8  test    eax, eax
0x4075ba  js      short loc_4075C3
0x4075bc  mov     esi, [esi+4]
0x4075bf  test    esi, esi
0x4075c1  jnz     short loc_407571
0x4075c3  pop     edi
0x4075c4  pop     esi
0x4075c5  leave
0x4075c6  retn
```
