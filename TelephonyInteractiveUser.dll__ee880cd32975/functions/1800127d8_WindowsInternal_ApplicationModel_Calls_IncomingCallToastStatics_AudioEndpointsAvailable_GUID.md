# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(_GUID)

- ea: `0x1800127d8`
- end: `0x1800128f9`
- name: `?_AudioEndpointsAvailable@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@IEAA_NU_GUID@@@Z`
- size: `289`
- prototype: `bool __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800130c0`
- `0x180015020`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x1800027c0`
- `0x180011e68`
- `0x1800127d8`
- `0x180019010`

## import_xrefs

- `PhoneOm!GetBluetoothHandsFreeLineInfo` at `0x180012823`
- `PhoneOm!GetBluetoothHandsFreeLineInfo` at `0x180012823`

## pseudocode

```c
bool __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        struct _GUID *a2)
{
  int BluetoothHandsFreeLineInfo; // eax
  __int64 v5; // r8
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v9[20]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+54h] [rbp-ACh]
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+260h] [rbp+160h] BYREF
  int *v12; // [rsp+280h] [rbp+180h]
  __int64 v13; // [rsp+288h] [rbp+188h]
  int *v14; // [rsp+290h] [rbp+190h]
  __int64 v15; // [rsp+298h] [rbp+198h]

  memset_0(v9, 0, 0x220u);
  BluetoothHandsFreeLineInfo = GetBluetoothHandsFreeLineInfo(a2, v9);
  if ( BluetoothHandsFreeLineInfo < 0 )
    Log_HREvent_1((unsigned int)BluetoothHandsFreeLineInfo, 0, v5, 629);
  if ( (unsigned int)dword_180025038 > 4 )
  {
    v7 = v10;
    v15 = 4;
    v8 = v9[0] & 4;
    v13 = 4;
    v14 = &v7;
    v12 = &v8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025038, (unsigned __int8 *)&byte_180020B47, 0, 0, 4u, &v11);
  }
  return (*(unsigned __int8 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *))(*(_QWORD *)this + 128LL))(this)
      && (v9[0] & 4) != 0
      && v10 != 2;
}

```

## disassembly

```asm
0x1800127d8  mov     [rsp-8+arg_10], rbx
0x1800127dd  mov     [rsp-8+arg_18], rdi
0x1800127e2  push    rbp
0x1800127e3  lea     rbp, [rsp-1B0h]
0x1800127eb  sub     rsp, 2B0h
0x1800127f2  mov     rax, cs:__security_cookie
0x1800127f9  xor     rax, rsp
0x1800127fc  mov     [rbp+1B0h+var_10], rax
0x180012803  mov     rbx, rdx
0x180012806  mov     rdi, rcx
0x180012809  xor     edx, edx; Val
0x18001280b  lea     rcx, [rsp+2B0h+var_270]; void *
0x180012810  mov     r8d, 220h; Size
0x180012816  call    memset_0
0x18001281b  lea     rdx, [rsp+2B0h+var_270]
0x180012820  mov     rcx, rbx
0x180012823  call    cs:__imp_GetBluetoothHandsFreeLineInfo
0x180012829  test    eax, eax
0x18001282b  jns     short loc_18001283C
0x18001282d  xor     edx, edx
0x18001282f  mov     r9d, 275h
0x180012835  mov     ecx, eax
0x180012837  call    Log_HREvent_1
0x18001283c  mov     eax, cs:dword_180025038
0x180012842  mov     ebx, 4
0x180012847  cmp     eax, ebx
0x180012849  jbe     short loc_1800128AC
0x18001284b  mov     eax, [rsp+2B0h+var_25C]
0x18001284f  lea     rdx, byte_180020B47; int
0x180012856  mov     [rsp+2B0h+var_280], eax
0x18001285a  lea     rcx, dword_180025038; int
0x180012861  mov     eax, dword ptr [rsp+2B0h+var_270]
0x180012865  xor     r9d, r9d; int
0x180012868  and     eax, ebx
0x18001286a  mov     [rbp+1B0h+var_18], rbx
0x180012871  mov     [rsp+2B0h+var_27C], eax
0x180012875  xor     r8d, r8d; int
0x180012878  lea     rax, [rsp+2B0h+var_280]
0x18001287d  mov     [rbp+1B0h+var_28], rbx
0x180012884  mov     [rbp+1B0h+var_20], rax
0x18001288b  lea     rax, [rsp+2B0h+var_27C]
0x180012890  mov     [rbp+1B0h+var_30], rax
0x180012897  lea     rax, [rbp+1B0h+var_50]
0x18001289e  mov     [rsp+2B0h+var_288], rax; PEVENT_DATA_DESCRIPTOR
0x1800128a3  mov     [rsp+2B0h+var_290], ebx; ULONG
0x1800128a7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800128ac  mov     rax, [rdi]
0x1800128af  mov     rcx, rdi
0x1800128b2  mov     rax, [rax+80h]
0x1800128b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128be  test    al, al
0x1800128c0  jz      short loc_1800128D3
0x1800128c2  test    [rsp+2B0h+var_270], bl
0x1800128c6  jz      short loc_1800128D3
0x1800128c8  cmp     [rsp+2B0h+var_25C], 2
0x1800128cd  jz      short loc_1800128D3
0x1800128cf  mov     al, 1
0x1800128d1  jmp     short loc_1800128D5
0x1800128d3  xor     al, al
0x1800128d5  mov     rcx, [rbp+1B0h+var_10]
0x1800128dc  xor     rcx, rsp; StackCookie
0x1800128df  call    __security_check_cookie
0x1800128e4  lea     r11, [rsp+2B0h+var_s0]
0x1800128ec  mov     rbx, [r11+20h]
0x1800128f0  mov     rdi, [r11+28h]
0x1800128f4  mov     rsp, r11
0x1800128f7  pop     rbp
0x1800128f8  retn
```
