# SystemSettings::StorageSenseHandlers::CAppInfo::Create(HSTRING__ *,SystemSettings::StorageSenseHandlers::CAppInfo * *)

- ea: `0x180052354`
- end: `0x1800523d1`
- name: `?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAV123@@Z`
- size: `125`
- prototype: `__int64 __fastcall(HSTRING string, struct SystemSettings::StorageSenseHandlers::CAppInfo **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ea14`
- `0x18003ed98`

## callees

- `0x180004cfc`
- `0x180051aa8`
- `0x180052354`
- `0x180053ae8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800523a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800523a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005238d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005238d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::Create(HSTRING string, HSTRING **a2)
{
  HSTRING *v4; // rdi
  unsigned int v5; // ebx
  _QWORD *v6; // rbx
  const unsigned __int16 *v7; // rdx
  SystemSettings::StorageSenseHandlers::CAppInfo *v9; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>((__int64 *)&v9);
  v4 = (HSTRING *)v9;
  if ( v9 )
  {
    v6 = (_QWORD *)((char *)v9 + 104);
    WindowsDeleteString(*((HSTRING *)v9 + 13));
    *v6 = 0;
    WindowsDuplicateString(string, v4 + 13);
    v5 = SystemSettings::StorageSenseHandlers::CAppInfo::Init((SystemSettings::StorageSenseHandlers::CAppInfo *)v4, v7);
    v9 = 0;
    *a2 = v4;
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return v5;
}

```

## disassembly

```asm
0x180052354  push    rbx
0x180052356  push    rbp
0x180052357  push    rsi
0x180052358  push    rdi
0x180052359  sub     rsp, 28h
0x18005235d  mov     rsi, rdx
0x180052360  mov     rbp, rcx
0x180052363  mov     qword ptr [rdx], 0
0x18005236a  lea     rcx, [rsp+48h+arg_8]
0x18005236f  call    ??$Make@VCAppInfo@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppInfo@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>(void)
0x180052374  nop
0x180052375  mov     rdi, [rsp+48h+arg_8]
0x18005237a  test    rdi, rdi
0x18005237d  jnz     short loc_180052386
0x18005237f  mov     ebx, 8007000Eh
0x180052384  jmp     short loc_1800523BC
0x180052386  lea     rbx, [rdi+68h]
0x18005238a  mov     rcx, [rbx]; string
0x18005238d  call    cs:__imp_WindowsDeleteString
0x180052393  mov     qword ptr [rbx], 0
0x18005239a  mov     rdx, rbx; newString
0x18005239d  mov     rcx, rbp; string
0x1800523a0  call    cs:__imp_WindowsDuplicateString
0x1800523a6  mov     rcx, rdi; this
0x1800523a9  call    ?Init@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CAppInfo::Init(void)
0x1800523ae  mov     ebx, eax
0x1800523b0  mov     [rsp+48h+arg_8], 0
0x1800523b9  mov     [rsi], rdi
0x1800523bc  lea     rcx, [rsp+48h+arg_8]
0x1800523c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800523c6  mov     eax, ebx
0x1800523c8  add     rsp, 28h
0x1800523cc  pop     rdi
0x1800523cd  pop     rsi
0x1800523ce  pop     rbp
0x1800523cf  pop     rbx
0x1800523d0  retn
```
