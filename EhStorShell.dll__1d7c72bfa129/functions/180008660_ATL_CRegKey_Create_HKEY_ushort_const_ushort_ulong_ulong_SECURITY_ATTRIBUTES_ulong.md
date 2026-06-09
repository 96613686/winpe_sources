# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180008660`
- end: `0x1800086df`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004fb8`

## callees

- `0x180006820`
- `0x180008660`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800086b9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800086b9`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4, unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x180008660  mov     r11, rsp
0x180008663  mov     [r11+20h], r9
0x180008667  push    rbx
0x180008668  sub     rsp, 50h
0x18000866c  mov     rbx, rcx
0x18000866f  mov     dword ptr [r11+28h], 0
0x180008677  lea     rcx, [r11+28h]
0x18000867b  mov     qword ptr [r11+20h], 0
0x180008683  mov     [r11-18h], rcx
0x180008687  mov     rax, r8
0x18000868a  lea     rcx, [r11+20h]
0x18000868e  mov     r10, rdx
0x180008691  mov     [r11-20h], rcx
0x180008695  xor     r9d, r9d; lpClass
0x180008698  mov     qword ptr [r11-28h], 0
0x1800086a0  xor     r8d, r8d; Reserved
0x1800086a3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800086ab  mov     rdx, rax; lpSubKey
0x1800086ae  mov     rcx, r10; hKey
0x1800086b1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800086b9  call    cs:__imp_RegCreateKeyExW
0x1800086bf  mov     ecx, eax
0x1800086c1  test    eax, eax
0x1800086c3  jnz     short loc_1800086D7
0x1800086c5  mov     rcx, rbx; this
0x1800086c8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800086cd  mov     ecx, eax
0x1800086cf  mov     rax, [rsp+58h+arg_18]
0x1800086d4  mov     [rbx], rax
0x1800086d7  mov     eax, ecx
0x1800086d9  add     rsp, 50h
0x1800086dd  pop     rbx
0x1800086de  retn
```
