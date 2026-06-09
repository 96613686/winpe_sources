# GetUpdateReserveManagerCBS

- ea: `0x18000c9c0`
- end: `0x18000cac9`
- name: `GetUpdateReserveManagerCBS`
- size: `265`
- prototype: `__int64 __fastcall(__int64, char, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180003c84`
- `0x18000473c`
- `0x180005e60`
- `0x18000c9c0`
- `0x18000fafc`
- `0x1800177f8`

## string_xrefs

- `0x18000ca08`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`
- `0x18000ca14`: `GetUpdateReserveManagerCBS`

## pseudocode

```c
__int64 __fastcall GetUpdateReserveManagerCBS(__int64 a1, char a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // edi
  _QWORD v12[10]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v12[4] = -2;
  v8 = 0;
  if ( a2 )
    v8 = 2;
  try
  {
    if ( Windows::AutoNewPtr<UpdateReserveManager>::Allocate<>() )
    {
      v11 = UpdateReserveManager::Initialize(0, v8, a1, a3, a4);
      if ( v11 >= 0 )
      {
        *a5 = 0;
        result = 0;
      }
      else
      {
        result = (unsigned int)v11;
      }
    }
    else
    {
      v12[0] = "onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp";
      v12[1] = "GetUpdateReserveManagerCBS";
      v12[2] = 77;
      v12[3] = "ReserveManager.Allocate()";
      RtlReportErrorOrigination(v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942414LL);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x57,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  push    rsi
0x18000c9c3  push    rdi
0x18000c9c4  push    r14
0x18000c9c6  push    r15
0x18000c9c8  sub     rsp, 60h
0x18000c9cc  mov     [rsp+88h+var_30], 0FFFFFFFFFFFFFFFEh
0x18000c9d5  mov     r15, r9
0x18000c9d8  mov     r14, r8
0x18000c9db  mov     rdi, rcx
0x18000c9de  mov     rsi, [rsp+88h+arg_20]
0x18000c9e6  xor     ebx, ebx
0x18000c9e8  lea     eax, [rbx+2]
0x18000c9eb  test    dl, dl
0x18000c9ed  cmovnz  ebx, eax
0x18000c9f0  mov     [rsp+88h+var_58], 0
0x18000c9f9  lea     rcx, [rsp+88h+var_58]
0x18000c9fe  call    ??$Allocate@$$V@?$AutoNewPtr@VUpdateReserveManager@@@Windows@@QEAAPEAVUpdateReserveManager@@XZ; Windows::AutoNewPtr<UpdateReserveManager>::Allocate<>(void)
0x18000ca03  test    rax, rax
0x18000ca06  jnz     short loc_18000CA73
0x18000ca08  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x18000ca0f  mov     [rsp+88h+var_50], rax
0x18000ca14  lea     rax, aGetupdatereser_1; "GetUpdateReserveManagerCBS"
0x18000ca1b  mov     [rsp+88h+var_48], rax
0x18000ca20  mov     [rsp+88h+var_40], 4Dh ; 'M'
0x18000ca29  lea     rax, aReservemanager_1; "ReserveManager.Allocate()"
0x18000ca30  mov     [rsp+88h+var_38], rax
0x18000ca35  mov     r8d, 8007000Eh
0x18000ca3b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18000ca42  lea     rcx, [rsp+88h+var_50]
0x18000ca47  call    RtlReportErrorOrigination
0x18000ca4c  nop
0x18000ca4d  mov     rbx, [rsp+88h+var_58]
0x18000ca52  test    rbx, rbx
0x18000ca55  jz      short loc_18000CA6C
0x18000ca57  mov     rcx, rbx; this
0x18000ca5a  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x18000ca5f  mov     edx, 538h; unsigned __int64
0x18000ca64  mov     rcx, rbx; void *
0x18000ca67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ca6c  mov     eax, 8007000Eh
0x18000ca71  jmp     short loc_18000CABC
0x18000ca73  mov     [rsp+88h+var_68], r15
0x18000ca78  mov     r9, r14
0x18000ca7b  mov     r8, rdi
0x18000ca7e  mov     edx, ebx
0x18000ca80  mov     rbx, [rsp+88h+var_58]
0x18000ca85  mov     rcx, rbx
0x18000ca88  call    ?Initialize@UpdateReserveManager@@QEAAJW4InitializeManagerFlags@1@QEB_W1QEBD@Z; UpdateReserveManager::Initialize(UpdateReserveManager::InitializeManagerFlags,wchar_t const * const,wchar_t const * const,char const * const)
0x18000ca8d  mov     edi, eax
0x18000ca8f  test    eax, eax
0x18000ca91  jns     short loc_18000CAB1
0x18000ca93  test    rbx, rbx
0x18000ca96  jz      short loc_18000CAAD
0x18000ca98  mov     rcx, rbx; this
0x18000ca9b  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x18000caa0  mov     edx, 538h; unsigned __int64
0x18000caa5  mov     rcx, rbx; void *
0x18000caa8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000caad  mov     eax, edi
0x18000caaf  jmp     short loc_18000CABC
0x18000cab1  mov     [rsi], rbx
0x18000cab4  xor     eax, eax
0x18000cab6  jmp     short loc_18000CABC
0x18000cab8  mov     eax, dword ptr [rsp+88h+var_58]
0x18000cabc  add     rsp, 60h
0x18000cac0  pop     r15
0x18000cac2  pop     r14
0x18000cac4  pop     rdi
0x18000cac5  pop     rsi
0x18000cac6  pop     rbx
0x18000cac7  retn
```
