# GetUpdateReserveManagerPrivate(wchar_t const * const,wchar_t const * const,char const * const,UpdateReserveManager * *)

- ea: `0x180007d08`
- end: `0x180007e01`
- name: `?GetUpdateReserveManagerPrivate@@YAJQEB_W0QEBDPEAPEAVUpdateReserveManager@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const char *, struct UpdateReserveManager **)`
- caller_count: `9`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c520`
- `0x18000c610`
- `0x18000c6b0`
- `0x18000c760`
- `0x18000c820`
- `0x18000cad0`
- `0x18000cb70`
- `0x18000cc20`
- `0x18000ccd0`

## callees

- `0x180003c84`
- `0x18000473c`
- `0x180005e60`
- `0x180007d08`
- `0x18000fafc`
- `0x1800177f8`

## string_xrefs

- `0x180007d3f`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`
- `0x180007d4b`: `GetUpdateReserveManagerPrivate`

## pseudocode

```c
__int64 __fastcall GetUpdateReserveManagerPrivate(
        const wchar_t *a1,
        const wchar_t *a2,
        const char *a3,
        struct UpdateReserveManager **a4)
{
  const char *v8; // r9
  __int64 result; // rax
  int v10; // edi
  _QWORD v11[10]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11[4] = -2;
  try
  {
    if ( Windows::AutoNewPtr<UpdateReserveManager>::Allocate<>() )
    {
      v10 = UpdateReserveManager::Initialize(0, 1, a1, a2, a3);
      if ( v10 >= 0 )
      {
        *a4 = 0;
        result = 0;
      }
      else
      {
        result = (unsigned int)v10;
      }
    }
    else
    {
      v11[0] = "onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp";
      v11[1] = "GetUpdateReserveManagerPrivate";
      v11[2] = 99;
      v11[3] = "ReserveManager.Allocate()";
      RtlReportErrorOrigination(v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942414LL);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6D,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180007d08  push    rbx
0x180007d0a  push    rsi
0x180007d0b  push    rdi
0x180007d0c  push    r14
0x180007d0e  sub     rsp, 68h
0x180007d12  mov     [rsp+88h+var_30], 0FFFFFFFFFFFFFFFEh
0x180007d1b  mov     rsi, r9
0x180007d1e  mov     r14, r8
0x180007d21  mov     rdi, rdx
0x180007d24  mov     rbx, rcx
0x180007d27  mov     [rsp+88h+var_58], 0
0x180007d30  lea     rcx, [rsp+88h+var_58]
0x180007d35  call    ??$Allocate@$$V@?$AutoNewPtr@VUpdateReserveManager@@@Windows@@QEAAPEAVUpdateReserveManager@@XZ; Windows::AutoNewPtr<UpdateReserveManager>::Allocate<>(void)
0x180007d3a  test    rax, rax
0x180007d3d  jnz     short loc_180007DAA
0x180007d3f  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180007d46  mov     [rsp+88h+var_50], rax
0x180007d4b  lea     rax, aGetupdatereser_3; "GetUpdateReserveManagerPrivate"
0x180007d52  mov     [rsp+88h+var_48], rax
0x180007d57  mov     [rsp+88h+var_40], 63h ; 'c'
0x180007d60  lea     rax, aReservemanager_1; "ReserveManager.Allocate()"
0x180007d67  mov     [rsp+88h+var_38], rax
0x180007d6c  mov     r8d, 8007000Eh
0x180007d72  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180007d79  lea     rcx, [rsp+88h+var_50]
0x180007d7e  call    RtlReportErrorOrigination
0x180007d83  nop
0x180007d84  mov     rbx, [rsp+88h+var_58]
0x180007d89  test    rbx, rbx
0x180007d8c  jz      short loc_180007DA3
0x180007d8e  mov     rcx, rbx; this
0x180007d91  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x180007d96  mov     edx, 538h; unsigned __int64
0x180007d9b  mov     rcx, rbx; void *
0x180007d9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007da3  mov     eax, 8007000Eh
0x180007da8  jmp     short loc_180007DF6
0x180007daa  mov     [rsp+88h+var_68], r14
0x180007daf  mov     r9, rdi
0x180007db2  mov     r8, rbx
0x180007db5  mov     edx, 1
0x180007dba  mov     rbx, [rsp+88h+var_58]
0x180007dbf  mov     rcx, rbx
0x180007dc2  call    ?Initialize@UpdateReserveManager@@QEAAJW4InitializeManagerFlags@1@QEB_W1QEBD@Z; UpdateReserveManager::Initialize(UpdateReserveManager::InitializeManagerFlags,wchar_t const * const,wchar_t const * const,char const * const)
0x180007dc7  mov     edi, eax
0x180007dc9  test    eax, eax
0x180007dcb  jns     short loc_180007DEB
0x180007dcd  test    rbx, rbx
0x180007dd0  jz      short loc_180007DE7
0x180007dd2  mov     rcx, rbx; this
0x180007dd5  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x180007dda  mov     edx, 538h; unsigned __int64
0x180007ddf  mov     rcx, rbx; void *
0x180007de2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007de7  mov     eax, edi
0x180007de9  jmp     short loc_180007DF6
0x180007deb  mov     [rsi], rbx
0x180007dee  xor     eax, eax
0x180007df0  jmp     short loc_180007DF6
0x180007df2  mov     eax, dword ptr [rsp+88h+var_58]
0x180007df6  add     rsp, 68h
0x180007dfa  pop     r14
0x180007dfc  pop     rdi
0x180007dfd  pop     rsi
0x180007dfe  pop     rbx
0x180007dff  retn
```
