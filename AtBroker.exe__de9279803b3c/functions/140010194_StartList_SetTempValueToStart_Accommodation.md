# StartList::SetTempValueToStart(Accommodation *)

- ea: `0x140010194`
- end: `0x14001023d`
- name: `?SetTempValueToStart@StartList@@AEAAXPEAVAccommodation@@@Z`
- size: `169`
- prototype: `void __fastcall(StartList *this, const WCHAR **, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010244`

## callees

- `0x14000be54`
- `0x140010194`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140010231`
- `ADVAPI32!RegCloseKey` at `0x140010231`
- `KERNEL32!RegSetValueExW` at `0x140010223`
- `KERNEL32!RegSetValueExW` at `0x140010223`

## string_xrefs

- `0x1400101a8`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
void __fastcall StartList::SetTempValueToStart(StartList *this, const WCHAR **a2, __int64 a3, unsigned __int16 *a4)
{
  HKEY v5; // rcx
  const WCHAR *v6; // rdx
  HKEY v7; // rbx
  struct _SECURITY_ATTRIBUTES *v8; // [rsp+30h] [rbp-38h]
  HKEY hKey[5]; // [rsp+40h] [rbp-28h] BYREF
  StartList *Data; // [rsp+70h] [rbp+8h] BYREF

  Data = this;
  memset(hKey, 0, 24);
  if ( ATL::CRegKey::Create(
         (ATL::CRegKey *)hKey,
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
         a4,
         1u,
         0x2001Fu,
         v8,
         0) )
  {
    v5 = hKey[0];
    if ( !hKey[0] )
      return;
  }
  else
  {
    v6 = *a2;
    v7 = hKey[0];
    LODWORD(Data) = 3;
    RegSetValueExW(hKey[0], v6, 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v7 )
      return;
    v5 = v7;
  }
  RegCloseKey(v5);
}

```

## disassembly

```asm
0x140010194  mov     rax, rsp
0x140010197  mov     [rax+8], rcx
0x14001019b  push    rbx
0x14001019c  sub     rsp, 60h
0x1400101a0  mov     qword ptr [rax-30h], 0
0x1400101a8  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400101af  mov     rbx, rdx
0x1400101b2  mov     dword ptr [rax-40h], 2001Fh
0x1400101b9  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x1400101c0  mov     dword ptr [rax-48h], 1
0x1400101c7  lea     rcx, [rax-28h]; this
0x1400101cb  mov     qword ptr [rax-28h], 0
0x1400101d3  mov     qword ptr [rax-20h], 0
0x1400101db  mov     qword ptr [rax-18h], 0
0x1400101e3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400101e8  test    eax, eax
0x1400101ea  jz      short loc_1400101F8
0x1400101ec  mov     rcx, [rsp+68h+hKey]
0x1400101f1  test    rcx, rcx
0x1400101f4  jz      short loc_140010237
0x1400101f6  jmp     short loc_140010231
0x1400101f8  mov     rdx, [rbx]; lpValueName
0x1400101fb  lea     rax, [rsp+68h+Data]
0x140010200  mov     rbx, [rsp+68h+hKey]
0x140010205  mov     r9d, 4; dwType
0x14001020b  mov     [rsp+68h+cbData], r9d; cbData
0x140010210  mov     rcx, rbx; hKey
0x140010213  xor     r8d, r8d; Reserved
0x140010216  mov     dword ptr [rsp+68h+Data], 3
0x14001021e  mov     [rsp+68h+lpData], rax; lpData
0x140010223  call    cs:__imp_RegSetValueExW
0x140010229  test    rbx, rbx
0x14001022c  jz      short loc_140010237
0x14001022e  mov     rcx, rbx; hKey
0x140010231  call    cs:__imp_RegCloseKey
0x140010237  add     rsp, 60h
0x14001023b  pop     rbx
0x14001023c  retn
```
