# Windows::Networking::UX::Internal::MBCategory::_DeleteWwanProfileFromService(ushort const *,Windows::Networking::UX::MbConnectionProfileType)

- ea: `0x1800430d8`
- end: `0x18004317f`
- name: `?_DeleteWwanProfileFromService@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEBGW4MbConnectionProfileType@345@@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180041260`

## callees

- `0x180008c84`
- `0x1800430d8`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteDMConfigProfile` at `0x18004314b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteDMConfigProfile` at `0x18004314b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x1800430fb`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x1800430fb`

## string_xrefs

- `0x180043114`: `Failed to call WwanDeleteProfile. profileName=%ls, HRESULT=0x%x`
- `0x180043127`: `Windows::Networking::UX::Internal::MBCategory::_DeleteWwanProfileFromService`
- `0x180043164`: `Failed to call WwanDeleteDMConfigProfile. profileName=%ls, HRESULT=0x%x`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_DeleteWwanProfileFromService(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v4; // eax
  signed int v5; // ebx
  const char *v6; // r8
  unsigned int v7; // edx
  int v9; // eax
  signed int v10; // [rsp+20h] [rbp-18h]

  if ( a3 )
  {
    if ( a3 == 1 )
    {
      v9 = WwanDeleteDMConfigProfile(*(_QWORD *)(a1 + 304), a1 + 24, a2);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 < 0 )
      {
        v6 = "Failed to call WwanDeleteDMConfigProfile. profileName=%ls, HRESULT=0x%x";
        v7 = 4636;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v4 = WwanDeleteProfile(*(_QWORD *)(a1 + 304), a1 + 24, a2, 0);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = "Failed to call WwanDeleteProfile. profileName=%ls, HRESULT=0x%x";
      v7 = 4623;
LABEL_6:
      v10 = v5;
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_DeleteWwanProfileFromService",
        v7,
        v6,
        a2,
        v10);
      return (unsigned int)v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800430d8  mov     [rsp+arg_0], rbx
0x1800430dd  push    rdi
0x1800430de  sub     rsp, 30h
0x1800430e2  mov     rdi, rdx
0x1800430e5  test    r8d, r8d
0x1800430e8  jnz     short loc_180043137
0x1800430ea  lea     rdx, [rcx+18h]
0x1800430ee  xor     r9d, r9d
0x1800430f1  mov     rcx, [rcx+130h]
0x1800430f8  mov     r8, rdi
0x1800430fb  call    cs:__imp_WwanDeleteProfile
0x180043101  mov     ebx, eax
0x180043103  test    eax, eax
0x180043105  jle     short loc_180043110
0x180043107  movzx   ebx, ax
0x18004310a  or      ebx, 80070000h
0x180043110  test    ebx, ebx
0x180043112  jns     short loc_180043172
0x180043114  lea     r8, aFailedToCallWw; "Failed to call WwanDeleteProfile. profi"...
0x18004311b  mov     edx, 120Fh; unsigned int
0x180043120  mov     r9, rdi
0x180043123  mov     [rsp+38h+var_18], ebx
0x180043127  lea     rcx, aWindowsNetwork_169; "Windows::Networking::UX::Internal::MBCa"...
0x18004312e  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180043133  mov     eax, ebx
0x180043135  jmp     short loc_180043174
0x180043137  cmp     r8d, 1
0x18004313b  jnz     short loc_180043172
0x18004313d  lea     rdx, [rcx+18h]
0x180043141  mov     r8, rdi
0x180043144  mov     rcx, [rcx+130h]
0x18004314b  call    cs:__imp_WwanDeleteDMConfigProfile
0x180043151  mov     ebx, eax
0x180043153  test    eax, eax
0x180043155  jle     short loc_180043160
0x180043157  movzx   ebx, ax
0x18004315a  or      ebx, 80070000h
0x180043160  test    ebx, ebx
0x180043162  jns     short loc_180043172
0x180043164  lea     r8, aFailedToCallWw_1; "Failed to call WwanDeleteDMConfigProfil"...
0x18004316b  mov     edx, 121Ch
0x180043170  jmp     short loc_180043120
0x180043172  xor     eax, eax
0x180043174  mov     rbx, [rsp+38h+arg_0]
0x180043179  add     rsp, 30h
0x18004317d  pop     rdi
0x18004317e  retn
```
