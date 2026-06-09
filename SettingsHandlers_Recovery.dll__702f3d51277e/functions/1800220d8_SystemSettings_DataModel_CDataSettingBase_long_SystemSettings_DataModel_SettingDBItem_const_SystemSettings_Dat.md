# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x1800220d8`
- end: `0x1800222d5`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `509`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013fc0`
- `0x18001f820`

## callees

- `0x1800220d8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022242`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180022119`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180022119`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800222af`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800222af`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800222ba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800222ba`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002213e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002213e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(
        _DWORD *a1,
        __int64 (***a2)(void))
{
  int v4; // eax
  bool v5; // r14
  char v6; // r15
  __int64 v7; // rcx
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // ebx
  unsigned int v11; // r8d
  const char *v12; // r9
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  int v20; // [rsp+58h] [rbp+10h] BYREF
  __int64 v21; // [rsp+60h] [rbp+18h]
  __int16 v22; // [rsp+68h] [rbp+20h]
  HRESULT v23; // [rsp+6Ch] [rbp+24h]

  v4 = a1[46];
  v5 = 0;
  v22 = 0;
  v6 = 0;
  v23 = 0;
  switch ( v4 )
  {
    case 1:
      v7 = 0;
LABEL_5:
      v8 = RoInitialize(v7);
      v23 = v8;
      v5 = v8 >= 0;
      LOBYTE(v22) = v8 >= 0;
      break;
    case 2:
      v7 = 1;
      goto LABEL_5;
    case 3:
      v9 = CoInitializeEx(0, 6u);
      v23 = v9;
      if ( v9 >= 0 )
      {
        v6 = 1;
        HIBYTE(v22) = 1;
      }
      break;
  }
  v21 = 0;
  try
  {
    v10 = (**a2)();
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 232LL))(a1, v21);
      if ( v10 == -2147467263 )
      {
        v20 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 48LL))(v21, &v20);
        if ( v10 >= 0 )
        {
          if ( v20 == 11 )
          {
            LOBYTE(string) = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 144LL))(v21, &string);
            if ( v10 >= 0 )
            {
              LOBYTE(v15) = (_BYTE)string != 0;
              v10 = (*(__int64 (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 216LL))(a1, v15);
            }
          }
          else if ( v20 == 12 )
          {
            string = 0;
            v13 = v21;
            v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 152LL);
            WindowsDeleteString(0);
            string = 0;
            v10 = v14(v13, &string);
            if ( v10 >= 0 )
              v10 = (*(__int64 (__fastcall **)(_DWORD *, HSTRING))(*(_QWORD *)a1 + 224LL))(a1, string);
            WindowsDeleteString(string);
          }
          else
          {
            v10 = -2147024809;
          }
        }
      }
    }
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( v5 )
      RoUninitialize();
    if ( v6 )
      CoUninitialize();
    result = (unsigned int)v10;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x973, v11, v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800220d8  push    rbx
0x1800220da  push    rsi
0x1800220db  push    rdi
0x1800220dc  push    r14
0x1800220de  push    r15
0x1800220e0  sub     rsp, 20h
0x1800220e4  mov     rbx, rdx
0x1800220e7  mov     rsi, rcx
0x1800220ea  mov     eax, [rcx+0B8h]
0x1800220f0  xor     r14b, r14b
0x1800220f3  mov     [rsp+48h+arg_18], 0
0x1800220fa  xor     r15b, r15b
0x1800220fd  mov     [rsp+48h+arg_1C], 0
0x180022105  mov     edi, 1
0x18002210a  cmp     eax, edi
0x18002210c  jnz     short loc_180022112
0x18002210e  xor     ecx, ecx
0x180022110  jmp     short loc_180022119
0x180022112  cmp     eax, 2
0x180022115  jnz     short loc_180022134
0x180022117  mov     ecx, edi
0x180022119  call    cs:__imp_RoInitialize
0x18002211f  mov     [rsp+48h+arg_1C], eax
0x180022123  movzx   r14d, r14b
0x180022127  test    eax, eax
0x180022129  cmovns  r14d, edi
0x18002212d  mov     byte ptr [rsp+48h+arg_18], r14b
0x180022132  jmp     short loc_180022154
0x180022134  cmp     eax, 3
0x180022137  jnz     short loc_180022154
0x180022139  lea     edx, [rax+3]; dwCoInit
0x18002213c  xor     ecx, ecx; pvReserved
0x18002213e  call    cs:__imp_CoInitializeEx
0x180022144  mov     [rsp+48h+arg_1C], eax
0x180022148  test    eax, eax
0x18002214a  js      short loc_180022154
0x18002214c  mov     r15b, dil
0x18002214f  mov     byte ptr [rsp+48h+arg_18+1], dil
0x180022154  mov     [rsp+48h+arg_10], 0
0x18002215d  mov     rax, [rbx]
0x180022160  lea     r8, [rsp+48h+arg_10]
0x180022165  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18002216c  mov     rcx, rbx
0x18002216f  mov     rax, [rax]
0x180022172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022177  mov     ebx, eax
0x180022179  test    eax, eax
0x18002217b  js      loc_18002228A
0x180022181  mov     rax, [rsi]
0x180022184  mov     rdx, [rsp+48h+arg_10]
0x180022189  mov     rcx, rsi
0x18002218c  mov     rax, [rax+0E8h]
0x180022193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022198  mov     ebx, eax
0x18002219a  cmp     eax, 80004001h
0x18002219f  jnz     loc_18002228A
0x1800221a5  mov     [rsp+48h+arg_8], 0
0x1800221ad  mov     rcx, [rsp+48h+arg_10]
0x1800221b2  mov     rax, [rcx]
0x1800221b5  lea     rdx, [rsp+48h+arg_8]
0x1800221ba  mov     rax, [rax+30h]
0x1800221be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c3  mov     ebx, eax
0x1800221c5  test    eax, eax
0x1800221c7  js      loc_18002228A
0x1800221cd  mov     ecx, [rsp+48h+arg_8]
0x1800221d1  sub     ecx, 0Bh
0x1800221d4  jz      short loc_18002224A
0x1800221d6  cmp     ecx, 1
0x1800221d9  jz      short loc_1800221E5
0x1800221db  mov     ebx, 80070057h
0x1800221e0  jmp     loc_18002228A
0x1800221e5  mov     [rsp+48h+string], 0
0x1800221ee  mov     rdi, [rsp+48h+arg_10]
0x1800221f3  mov     rax, [rdi]
0x1800221f6  mov     rbx, [rax+98h]
0x1800221fd  xor     ecx, ecx; string
0x1800221ff  call    cs:__imp_WindowsDeleteString
0x180022205  mov     [rsp+48h+string], 0
0x18002220e  lea     rdx, [rsp+48h+string]
0x180022213  mov     rcx, rdi
0x180022216  mov     rax, rbx
0x180022219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002221e  mov     ebx, eax
0x180022220  test    eax, eax
0x180022222  js      short loc_18002223D
0x180022224  mov     rax, [rsi]
0x180022227  mov     rdx, [rsp+48h+string]
0x18002222c  mov     rcx, rsi
0x18002222f  mov     rax, [rax+0E0h]
0x180022236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002223b  mov     ebx, eax
0x18002223d  mov     rcx, [rsp+48h+string]; string
0x180022242  call    cs:__imp_WindowsDeleteString
0x180022248  jmp     short loc_18002228A
0x18002224a  mov     byte ptr [rsp+48h+string], 0
0x18002224f  mov     rcx, [rsp+48h+arg_10]
0x180022254  mov     rax, [rcx]
0x180022257  lea     rdx, [rsp+48h+string]
0x18002225c  mov     rax, [rax+90h]
0x180022263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022268  mov     ebx, eax
0x18002226a  test    eax, eax
0x18002226c  js      short loc_18002228A
0x18002226e  mov     rax, [rsi]
0x180022271  cmp     byte ptr [rsp+48h+string], 0
0x180022276  setnz   dl
0x180022279  mov     rcx, rsi
0x18002227c  mov     rax, [rax+0D8h]
0x180022283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022288  mov     ebx, eax
0x18002228a  mov     rcx, [rsp+48h+arg_10]
0x18002228f  test    rcx, rcx
0x180022292  jz      short loc_1800222AA
0x180022294  mov     [rsp+48h+arg_10], 0
0x18002229d  mov     rax, [rcx]
0x1800222a0  mov     rax, [rax+10h]
0x1800222a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222a9  nop
0x1800222aa  test    r14b, r14b
0x1800222ad  jz      short loc_1800222B5
0x1800222af  call    cs:__imp_RoUninitialize
0x1800222b5  test    r15b, r15b
0x1800222b8  jz      short loc_1800222C0
0x1800222ba  call    cs:__imp_CoUninitialize
0x1800222c0  mov     eax, ebx
0x1800222c2  jmp     short loc_1800222C8
0x1800222c4  mov     eax, dword ptr [rsp+48h+string]
0x1800222c8  add     rsp, 20h
0x1800222cc  pop     r15
0x1800222ce  pop     r14
0x1800222d0  pop     rdi
0x1800222d1  pop     rsi
0x1800222d2  pop     rbx
0x1800222d3  retn
```
