# CWinRTextRange::put_ContentLinkInfo(Windows::UI::Text::IContentLinkInfo *)

- ea: `0x1801e37c0`
- end: `0x1801e39df`
- name: `?put_ContentLinkInfo@CWinRTextRange@@UEAAJPEAUIContentLinkInfo@Text@UI@Windows@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(CWinRTextRange *__hidden this, struct Windows::UI::Text::IContentLinkInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180021928`
- `0x180048d5c`
- `0x1801376bc`
- `0x1801e0c64`
- `0x1801e37c0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e3937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e394f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e3937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e394f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e39b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e39b7`

## pseudocode

```c
__int64 __fastcall CWinRTextRange::put_ContentLinkInfo(
        CWinRTextRange *this,
        struct Windows::UI::Text::IContentLinkInfo *a2)
{
  char *v5; // r14
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rax
  void (__fastcall *v9)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *); // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v13; // rax
  unsigned int v14; // ebx
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v18; // [rsp+48h] [rbp-11h] BYREF
  __int64 v19; // [rsp+50h] [rbp-9h] BYREF
  __int128 v20; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int16 *v21[2]; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int16 *v22; // [rsp+78h] [rbp+1Fh]
  _QWORD v23[6]; // [rsp+80h] [rbp+27h] BYREF
  unsigned int v24; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = (char *)this - 16;
  v26 = 0;
  v6 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  v7 = **v6;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v7(v6, &GUID_8d33f741_cf58_11ce_a89d_00aa006cadc5, &v26);
  v8 = *(_QWORD *)a2;
  v16 = 0;
  string = 0;
  v17 = 0;
  v9 = *(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(v8 + 64);
  v18 = 0;
  v19 = 0;
  v9(a2, &v17);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, HSTRING *))(*(_QWORD *)a2 + 80LL))(a2, &v18);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v16);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(*(_QWORD *)a2 + 112LL))(a2, &v19);
  (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 128LL))(v16, &string);
  if ( v17 )
    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v5 + 440LL))(v5, 0);
  v10 = *(_QWORD *)v5;
  v24 = 0;
  v25 = 0;
  (*(void (__fastcall **)(char *, unsigned int *))(v10 + 168))(v5, &v24);
  (*(void (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v5 + 96LL))(v5, &v25);
  v22 = 0;
  v20 = 0;
  *(_QWORD *)((char *)&v20 + 4) = __PAIR64__(v25, v24);
  v11 = *(_QWORD *)a2;
  *(_OWORD *)v21 = 0;
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, unsigned __int16 **))(v11 + 48))(a2, v21);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v21[1] = CW32System::SysAllocString(StringRawBuffer);
  v13 = WindowsGetStringRawBuffer(v18, 0);
  v22 = CW32System::SysAllocString(v13);
  CWinRTContentLinkInfo::GetLinkContentKindEnum((char *)this + 40, v19, (char *)&v20 + 12);
  v23[0] = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, _QWORD *))(*(_QWORD *)v26 + 24LL))(
          v26,
          1390,
          0,
          &v20,
          v23);
  CW32System::SysFreeString(v21[1]);
  CW32System::SysFreeString(v22);
  WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  return v14;
}

```

## disassembly

```asm
0x1801e37c0  mov     [rsp-8+arg_0], rbx
0x1801e37c5  push    rbp
0x1801e37c6  push    rsi
0x1801e37c7  push    rdi
0x1801e37c8  push    r14
0x1801e37ca  push    r15
0x1801e37cc  lea     rbp, [rsp-37h]
0x1801e37d1  sub     rsp, 90h
0x1801e37d8  mov     rsi, rdx
0x1801e37db  mov     r15, rcx
0x1801e37de  test    rdx, rdx
0x1801e37e1  jnz     short loc_1801E37ED
0x1801e37e3  mov     eax, 80070057h
0x1801e37e8  jmp     loc_1801E39C8
0x1801e37ed  lea     r14, [rcx-10h]
0x1801e37f1  mov     [rbp+57h+arg_18], 0
0x1801e37f9  mov     rdi, [r14+30h]
0x1801e37fd  lea     rcx, [rbp+57h+arg_18]
0x1801e3801  mov     rax, [rdi]
0x1801e3804  mov     rbx, [rax]
0x1801e3807  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e380c  lea     r8, [rbp+57h+arg_18]
0x1801e3810  mov     rcx, rdi
0x1801e3813  lea     rdx, _GUID_8d33f741_cf58_11ce_a89d_00aa006cadc5
0x1801e381a  mov     rax, rbx
0x1801e381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3822  mov     rax, [rsi]
0x1801e3825  lea     rdx, [rbp+57h+var_70]
0x1801e3829  mov     rcx, rsi
0x1801e382c  mov     [rbp+57h+var_78], 0
0x1801e3834  mov     [rbp+57h+string], 0
0x1801e383c  mov     [rbp+57h+var_70], 0
0x1801e3844  mov     rax, [rax+40h]
0x1801e3848  mov     [rbp+57h+var_68], 0
0x1801e3850  mov     [rbp+57h+var_60], 0
0x1801e3858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e385d  mov     rax, [rsi]
0x1801e3860  lea     rdx, [rbp+57h+var_68]
0x1801e3864  mov     rcx, rsi
0x1801e3867  mov     rax, [rax+50h]
0x1801e386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3870  mov     rax, [rsi]
0x1801e3873  lea     rdx, [rbp+57h+var_78]
0x1801e3877  mov     rcx, rsi
0x1801e387a  mov     rax, [rax+60h]
0x1801e387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3883  mov     rax, [rsi]
0x1801e3886  lea     rdx, [rbp+57h+var_60]
0x1801e388a  mov     rcx, rsi
0x1801e388d  mov     rax, [rax+70h]
0x1801e3891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3896  mov     rcx, [rbp+57h+var_78]
0x1801e389a  lea     rdx, [rbp+57h+string]
0x1801e389e  mov     rax, [rcx]
0x1801e38a1  mov     rax, [rax+80h]
0x1801e38a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e38ad  mov     r8, [rbp+57h+var_70]
0x1801e38b1  test    r8, r8
0x1801e38b4  jz      short loc_1801E38CA
0x1801e38b6  mov     rax, [r14]
0x1801e38b9  xor     edx, edx
0x1801e38bb  mov     rcx, r14
0x1801e38be  mov     rax, [rax+1B8h]
0x1801e38c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e38ca  mov     rax, [r14]
0x1801e38cd  lea     rdx, [rbp+57h+arg_8]
0x1801e38d1  mov     rcx, r14
0x1801e38d4  mov     [rbp+57h+arg_8], 0
0x1801e38db  mov     [rbp+57h+arg_10], 0
0x1801e38e2  mov     rax, [rax+0A8h]
0x1801e38e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e38ee  mov     rax, [r14]
0x1801e38f1  lea     rdx, [rbp+57h+arg_10]
0x1801e38f5  mov     rcx, r14
0x1801e38f8  mov     rax, [rax+60h]
0x1801e38fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3901  xor     eax, eax
0x1801e3903  lea     rdx, [rbp+57h+var_48]
0x1801e3907  mov     [rbp+57h+var_38], rax
0x1801e390b  xorps   xmm0, xmm0
0x1801e390e  mov     eax, [rbp+57h+arg_8]
0x1801e3911  mov     rcx, rsi
0x1801e3914  movups  [rbp+57h+var_58], xmm0
0x1801e3918  mov     dword ptr [rbp+57h+var_58+4], eax
0x1801e391b  mov     eax, [rbp+57h+arg_10]
0x1801e391e  mov     dword ptr [rbp+57h+var_58+8], eax
0x1801e3921  mov     rax, [rsi]
0x1801e3924  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1801e3928  mov     rax, [rax+30h]
0x1801e392c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e3931  mov     rcx, [rbp+57h+string]; string
0x1801e3935  xor     edx, edx; length
0x1801e3937  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e393d  mov     rcx, rax; unsigned __int16 *
0x1801e3940  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801e3945  mov     rcx, [rbp+57h+var_68]; string
0x1801e3949  xor     edx, edx; length
0x1801e394b  mov     [rbp+57h+var_48+8], rax
0x1801e394f  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e3955  mov     rcx, rax; unsigned __int16 *
0x1801e3958  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801e395d  mov     rdx, [rbp+57h+var_60]
0x1801e3961  lea     rcx, [r15+28h]
0x1801e3965  lea     r8, [rbp+57h+var_58+0Ch]
0x1801e3969  mov     [rbp+57h+var_38], rax
0x1801e396d  call    ?GetLinkContentKindEnum@CWinRTContentLinkInfo@@SAJQEBU?$pair@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUHSTRING__@@PEAI@Z; CWinRTContentLinkInfo::GetLinkContentKindEnum(std::pair<uint,std::wstring> const * const,HSTRING__ *,uint *)
0x1801e3972  mov     rcx, [rbp+57h+arg_18]
0x1801e3976  lea     rdx, [rbp+57h+var_30]
0x1801e397a  mov     [rbp+57h+var_30], 0
0x1801e3982  lea     r9, [rbp+57h+var_58]
0x1801e3986  mov     [rsp+0B0h+var_90], rdx
0x1801e398b  xor     r8d, r8d
0x1801e398e  mov     edx, 56Eh
0x1801e3993  mov     rax, [rcx]
0x1801e3996  mov     rax, [rax+18h]
0x1801e399a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e399f  mov     rcx, [rbp+57h+var_48+8]; unsigned __int16 *
0x1801e39a3  mov     ebx, eax
0x1801e39a5  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801e39aa  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x1801e39ae  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801e39b3  mov     rcx, [rbp+57h+string]; string
0x1801e39b7  call    cs:__imp_WindowsDeleteString
0x1801e39bd  lea     rcx, [rbp+57h+arg_18]
0x1801e39c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e39c6  mov     eax, ebx
0x1801e39c8  mov     rbx, [rsp+0B0h+arg_0]
0x1801e39d0  add     rsp, 90h
0x1801e39d7  pop     r15
0x1801e39d9  pop     r14
0x1801e39db  pop     rdi
0x1801e39dc  pop     rsi
0x1801e39dd  pop     rbp
0x1801e39de  retn
```
