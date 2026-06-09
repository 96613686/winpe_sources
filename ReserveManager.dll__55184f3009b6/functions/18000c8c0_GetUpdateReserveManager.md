# GetUpdateReserveManager

- ea: `0x18000c8c0`
- end: `0x18000c9b6`
- name: `GetUpdateReserveManager`
- size: `246`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180003c84`
- `0x18000473c`
- `0x180005e60`
- `0x18000c8c0`
- `0x18000fafc`
- `0x1800177f8`

## string_xrefs

- `0x18000c8f7`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`
- `0x18000c903`: `GetUpdateReserveManager`

## pseudocode

```c
__int64 __fastcall GetUpdateReserveManager(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
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
      v10 = UpdateReserveManager::Initialize(0, 0, a1, a2, a3);
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
      v11[1] = "GetUpdateReserveManager";
      v11[2] = 46;
      v11[3] = "ReserveManager.Allocate()";
      RtlReportErrorOrigination(v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942414LL);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x38,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000c8c0  push    rbx
0x18000c8c2  push    rsi
0x18000c8c3  push    rdi
0x18000c8c4  push    r14
0x18000c8c6  sub     rsp, 68h
0x18000c8ca  mov     [rsp+88h+var_30], 0FFFFFFFFFFFFFFFEh
0x18000c8d3  mov     rsi, r9
0x18000c8d6  mov     r14, r8
0x18000c8d9  mov     rdi, rdx
0x18000c8dc  mov     rbx, rcx
0x18000c8df  mov     [rsp+88h+var_58], 0
0x18000c8e8  lea     rcx, [rsp+88h+var_58]
0x18000c8ed  call    ??$Allocate@$$V@?$AutoNewPtr@VUpdateReserveManager@@@Windows@@QEAAPEAVUpdateReserveManager@@XZ; Windows::AutoNewPtr<UpdateReserveManager>::Allocate<>(void)
0x18000c8f2  test    rax, rax
0x18000c8f5  jnz     short loc_18000C962
0x18000c8f7  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x18000c8fe  mov     [rsp+88h+var_50], rax
0x18000c903  lea     rax, aGetupdatereser_2; "GetUpdateReserveManager"
0x18000c90a  mov     [rsp+88h+var_48], rax
0x18000c90f  mov     [rsp+88h+var_40], 2Eh ; '.'
0x18000c918  lea     rax, aReservemanager_1; "ReserveManager.Allocate()"
0x18000c91f  mov     [rsp+88h+var_38], rax
0x18000c924  mov     r8d, 8007000Eh
0x18000c92a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18000c931  lea     rcx, [rsp+88h+var_50]
0x18000c936  call    RtlReportErrorOrigination
0x18000c93b  nop
0x18000c93c  mov     rbx, [rsp+88h+var_58]
0x18000c941  test    rbx, rbx
0x18000c944  jz      short loc_18000C95B
0x18000c946  mov     rcx, rbx; this
0x18000c949  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x18000c94e  mov     edx, 538h; unsigned __int64
0x18000c953  mov     rcx, rbx; void *
0x18000c956  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c95b  mov     eax, 8007000Eh
0x18000c960  jmp     short loc_18000C9AB
0x18000c962  mov     [rsp+88h+var_68], r14
0x18000c967  mov     r9, rdi
0x18000c96a  mov     r8, rbx
0x18000c96d  xor     edx, edx
0x18000c96f  mov     rbx, [rsp+88h+var_58]
0x18000c974  mov     rcx, rbx
0x18000c977  call    ?Initialize@UpdateReserveManager@@QEAAJW4InitializeManagerFlags@1@QEB_W1QEBD@Z; UpdateReserveManager::Initialize(UpdateReserveManager::InitializeManagerFlags,wchar_t const * const,wchar_t const * const,char const * const)
0x18000c97c  mov     edi, eax
0x18000c97e  test    eax, eax
0x18000c980  jns     short loc_18000C9A0
0x18000c982  test    rbx, rbx
0x18000c985  jz      short loc_18000C99C
0x18000c987  mov     rcx, rbx; this
0x18000c98a  call    ??1UpdateReserveManager@@QEAA@XZ; UpdateReserveManager::~UpdateReserveManager(void)
0x18000c98f  mov     edx, 538h; unsigned __int64
0x18000c994  mov     rcx, rbx; void *
0x18000c997  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c99c  mov     eax, edi
0x18000c99e  jmp     short loc_18000C9AB
0x18000c9a0  mov     [rsi], rbx
0x18000c9a3  xor     eax, eax
0x18000c9a5  jmp     short loc_18000C9AB
0x18000c9a7  mov     eax, dword ptr [rsp+88h+var_58]
0x18000c9ab  add     rsp, 68h
0x18000c9af  pop     r14
0x18000c9b1  pop     rdi
0x18000c9b2  pop     rsi
0x18000c9b3  pop     rbx
0x18000c9b4  retn
```
