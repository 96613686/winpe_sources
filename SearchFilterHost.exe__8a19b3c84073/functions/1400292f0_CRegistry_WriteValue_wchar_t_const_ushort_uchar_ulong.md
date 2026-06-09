# CRegistry::WriteValue(wchar_t const *,ushort,uchar *,ulong)

- ea: `0x1400292f0`
- end: `0x140029359`
- name: `?WriteValue@CRegistry@@UEAAHPEB_WGPEAEK@Z`
- size: `105`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14002875c`
- `0x1400292f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002930c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002930c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029348`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140029338`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140029338`

## pseudocode

```c
__int64 __fastcall CRegistry::WriteValue(
        CRegistry *this,
        const wchar_t *a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        DWORD cbData)
{
  DWORD v6; // ecx
  DWORD v8; // eax
  HKEY v9; // r10
  const BYTE *lpData; // r11
  LSTATUS v11; // eax

  if ( !*((_QWORD *)this + 22) )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  v8 = ConvertDBTYPEToREGTYPE(a3);
  v11 = RegSetValueExW(v9, a2, 0, v8, lpData, cbData);
  if ( v11 )
  {
    v6 = v11;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x1400292f0  push    rbx
0x1400292f2  sub     rsp, 30h
0x1400292f6  mov     r10, [rcx+0B0h]
0x1400292fd  mov     r11, r9
0x140029300  mov     rbx, rdx
0x140029303  test    r10, r10
0x140029306  jnz     short loc_140029316
0x140029308  lea     ecx, [r10+6]; dwErrCode
0x14002930c  call    cs:__imp_SetLastError
0x140029312  xor     eax, eax
0x140029314  jmp     short loc_140029353
0x140029316  movzx   ecx, r8w; unsigned __int16
0x14002931a  call    ?ConvertDBTYPEToREGTYPE@@YAKG@Z; ConvertDBTYPEToREGTYPE(ushort)
0x14002931f  mov     r9d, eax; dwType
0x140029322  xor     r8d, r8d; Reserved
0x140029325  mov     eax, [rsp+38h+arg_20]
0x140029329  mov     rdx, rbx; lpValueName
0x14002932c  mov     [rsp+38h+cbData], eax; cbData
0x140029330  mov     rcx, r10; hKey
0x140029333  mov     [rsp+38h+lpData], r11; lpData
0x140029338  call    cs:__imp_RegSetValueExW
0x14002933e  test    eax, eax
0x140029340  jz      short loc_140029346
0x140029342  mov     ecx, eax
0x140029344  jmp     short loc_14002930C
0x140029346  xor     ecx, ecx; dwErrCode
0x140029348  call    cs:__imp_SetLastError
0x14002934e  mov     eax, 1
0x140029353  add     rsp, 30h
0x140029357  pop     rbx
0x140029358  retn
```
