# RadioManager::InsertJob(RM_JOB,wchar_t const *,IRadioInstance *,IUIRadioInstanceInternal *,bool,_DEVICE_RADIO_STATE)

- ea: `0x18001f090`
- end: `0x18001f20a`
- name: `?InsertJob@RadioManager@@UEAAJW4RM_JOB@@PEB_WPEAUIRadioInstance@@PEAUIUIRadioInstanceInternal@@_NW4_DEVICE_RADIO_STATE@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, struct IRadioInstance *, __int64, char, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001880`
- `0x180003fa0`
- `0x180006b98`
- `0x18000be90`
- `0x18001f090`
- `0x1800200dc`
- `0x1800219ec`
- `0x180021f9c`
- `0x18002214c`
- `0x180028010`

## string_xrefs

- `0x18001f11d`: `INSTANCE_REMOVE`
- `0x18001f131`: `Invalid combination of arguments passed (BUG)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RadioManager::InsertJob(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        struct IRadioInstance *a4,
        __int64 a5,
        char a6,
        unsigned int a7)
{
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // ebx
  const char *v13; // rax
  __int64 v15; // r9
  const char *v16; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-10h] BYREF

  if ( !a2 && !a4 || a2 == 1 && !a3 || a2 == 2 && !a3 )
    goto LABEL_10;
  if ( a2 != 3 )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        RadioManager::_RemoveInstance((RadioManager *)(a1 - 32), a3);
      }
      else if ( a2 == 2 )
      {
        RadioManager::_OnInstanceRadioChange(a1 - 32, a3, a7);
      }
    }
    else
    {
      RadioManager::_AddInstance((RadioManager *)(a1 - 32), a4);
    }
    return 0;
  }
  if ( a4 && a5 )
  {
    v17[0] = a5;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(v17);
    v16 = (const char *)a4;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v16);
    LOBYTE(v15) = a6;
    RadioManager::_SetInstanceRadio(a1 - 32, &v16, v17, v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    if ( v17[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[0] + 16LL))(v17[0]);
    return 0;
  }
LABEL_10:
  MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)dword_180037050 > 2 )
  {
    if ( a2 )
    {
      v11 = a2 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 == 1 )
            v13 = "SET_INSTANCE_RADIO";
          else
            v13 = "UNKNOWN";
        }
        else
        {
          v13 = "INSTANCE_RADIO_CHANGE";
        }
      }
      else
      {
        v13 = "INSTANCE_REMOVE";
      }
    }
    else
    {
      v13 = "INSTANCE_ADD";
    }
    v17[0] = v13;
    v16 = "Invalid combination of arguments passed (BUG)";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v10,
      &unk_18002F748);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f090  push    rbp
0x18001f092  push    rbx
0x18001f093  push    rsi
0x18001f094  push    rdi
0x18001f095  mov     rbp, rsp
0x18001f098  sub     rsp, 48h
0x18001f09c  mov     rsi, r9
0x18001f09f  mov     r10, r8
0x18001f0a2  mov     ebx, edx
0x18001f0a4  mov     rdi, rcx
0x18001f0a7  test    edx, edx
0x18001f0a9  jnz     short loc_18001F0B0
0x18001f0ab  test    r9, r9
0x18001f0ae  jz      short loc_18001F0DF
0x18001f0b0  cmp     ebx, 1
0x18001f0b3  jnz     short loc_18001F0BA
0x18001f0b5  test    r10, r10
0x18001f0b8  jz      short loc_18001F0DF
0x18001f0ba  cmp     ebx, 2
0x18001f0bd  jnz     short loc_18001F0C4
0x18001f0bf  test    r10, r10
0x18001f0c2  jz      short loc_18001F0DF
0x18001f0c4  mov     rcx, [rbp+arg_20]
0x18001f0c8  cmp     ebx, 3
0x18001f0cb  jnz     loc_18001F164
0x18001f0d1  test    rsi, rsi
0x18001f0d4  jz      short loc_18001F0DF
0x18001f0d6  test    rcx, rcx
0x18001f0d9  jnz     loc_18001F17F
0x18001f0df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f0e4  mov     eax, cs:dword_180037050
0x18001f0ea  cmp     eax, 2
0x18001f0ed  jbe     short loc_18001F15A
0x18001f0ef  test    ebx, ebx
0x18001f0f1  jz      short loc_18001F126
0x18001f0f3  sub     ebx, 1
0x18001f0f6  jz      short loc_18001F11D
0x18001f0f8  sub     ebx, 1
0x18001f0fb  jz      short loc_18001F114
0x18001f0fd  cmp     ebx, 1
0x18001f100  jz      short loc_18001F10B
0x18001f102  lea     rax, aUnknown; "UNKNOWN"
0x18001f109  jmp     short loc_18001F12D
0x18001f10b  lea     rax, aSetInstanceRad; "SET_INSTANCE_RADIO"
0x18001f112  jmp     short loc_18001F12D
0x18001f114  lea     rax, aInstanceRadioC; "INSTANCE_RADIO_CHANGE"
0x18001f11b  jmp     short loc_18001F12D
0x18001f11d  lea     rax, aInstanceRemove; "INSTANCE_REMOVE"
0x18001f124  jmp     short loc_18001F12D
0x18001f126  lea     rax, aInstanceAdd; "INSTANCE_ADD"
0x18001f12d  mov     [rbp+var_10], rax
0x18001f131  lea     rax, aInvalidCombina; "Invalid combination of arguments passed"...
0x18001f138  mov     [rbp+var_18], rax
0x18001f13c  lea     rax, [rbp+var_10]
0x18001f140  mov     [rsp+48h+var_20], rax
0x18001f145  lea     rax, [rbp+var_18]
0x18001f149  mov     [rsp+48h+var_28], rax
0x18001f14e  lea     rdx, unk_18002F748
0x18001f155  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001f15a  mov     eax, 80070057h
0x18001f15f  jmp     loc_18001F201
0x18001f164  test    ebx, ebx
0x18001f166  jz      loc_18001F1F3
0x18001f16c  sub     ebx, 1
0x18001f16f  jz      short loc_18001F1E5
0x18001f171  sub     ebx, 1
0x18001f174  jz      short loc_18001F1D3
0x18001f176  cmp     ebx, 1
0x18001f179  jnz     loc_18001F1FF
0x18001f17f  mov     [rbp+var_10], rcx
0x18001f183  lea     rcx, [rbp+var_10]
0x18001f187  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x18001f18c  nop
0x18001f18d  mov     [rbp+var_18], rsi
0x18001f191  lea     rcx, [rbp+var_18]
0x18001f195  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x18001f19a  nop
0x18001f19b  lea     rcx, [rdi-20h]
0x18001f19f  mov     r9b, [rbp+arg_28]
0x18001f1a3  lea     r8, [rbp+var_10]
0x18001f1a7  lea     rdx, [rbp+var_18]
0x18001f1ab  call    ?_SetInstanceRadio@RadioManager@@AEAAXAEBV?$ComPtr@UIRadioInstance@@@WRL@Microsoft@@AEBV?$ComPtr@UIUIRadioInstanceInternal@@@34@_N@Z; RadioManager::_SetInstanceRadio(Microsoft::WRL::ComPtr<IRadioInstance> const &,Microsoft::WRL::ComPtr<IUIRadioInstanceInternal> const &,bool)
0x18001f1b0  nop
0x18001f1b1  lea     rcx, [rbp+var_18]
0x18001f1b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f1ba  nop
0x18001f1bb  mov     rcx, [rbp+var_10]
0x18001f1bf  test    rcx, rcx
0x18001f1c2  jz      short loc_18001F1D1
0x18001f1c4  mov     rax, [rcx]
0x18001f1c7  mov     rax, [rax+10h]
0x18001f1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1d0  nop
0x18001f1d1  jmp     short loc_18001F1FF
0x18001f1d3  lea     rcx, [rdi-20h]
0x18001f1d7  mov     r8d, [rbp+arg_30]
0x18001f1db  mov     rdx, r10
0x18001f1de  call    ?_OnInstanceRadioChange@RadioManager@@AEAAXPEB_WW4_DEVICE_RADIO_STATE@@@Z; RadioManager::_OnInstanceRadioChange(wchar_t const *,_DEVICE_RADIO_STATE)
0x18001f1e3  jmp     short loc_18001F1FF
0x18001f1e5  lea     rcx, [rdi-20h]; this
0x18001f1e9  mov     rdx, r10; wchar_t *
0x18001f1ec  call    ?_RemoveInstance@RadioManager@@AEAAXPEB_W@Z; RadioManager::_RemoveInstance(wchar_t const *)
0x18001f1f1  jmp     short loc_18001F1FF
0x18001f1f3  lea     rcx, [rdi-20h]; this
0x18001f1f7  mov     rdx, rsi; struct IRadioInstance *
0x18001f1fa  call    ?_AddInstance@RadioManager@@AEAAXPEAUIRadioInstance@@@Z; RadioManager::_AddInstance(IRadioInstance *)
0x18001f1ff  xor     eax, eax
0x18001f201  add     rsp, 48h
0x18001f205  pop     rdi
0x18001f206  pop     rsi
0x18001f207  pop     rbx
0x18001f208  pop     rbp
0x18001f209  retn
```
