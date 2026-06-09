# DpspRaiseScenarioDispatchEvent

- ea: `0x180007694`
- end: `0x1800077fa`
- name: `DpspRaiseScenarioDispatchEvent`
- size: `358`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003830`
- `0x180004864`
- `0x180004de4`
- `0x1800118f0`
- `0x180011c6c`

## callees

- `0x180007694`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007723`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007723`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800077bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800077bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000774b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800077ce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000774b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800077ce`

## pseudocode

```c
__int64 __fastcall DpspRaiseScenarioDispatchEvent(__int64 a1, const EVENT_DESCRIPTOR *a2)
{
  unsigned int v4; // esi
  __int64 v5; // r8
  __int64 v6; // rax
  GUID ActivityId; // [rsp+30h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-19h] BYREF
  __int64 v10; // [rsp+50h] [rbp-9h]
  __int64 v11; // [rsp+58h] [rbp-1h]
  __int64 v12; // [rsp+60h] [rbp+7h]
  __int64 v13; // [rsp+68h] [rbp+Fh]
  __int64 v14; // [rsp+70h] [rbp+17h]
  int v15; // [rsp+78h] [rbp+1Fh]
  int v16; // [rsp+7Ch] [rbp+23h]
  __int64 v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  UserData.Ptr = 0;
  ActivityId = 0;
  memset_0(&UserData.Size, 0, 0x48u);
  if ( a1 )
  {
    v4 = 0;
    if ( EventEnabled(g_hETW, a2) )
    {
      if ( a1 != -24 )
        ActivityId = *(GUID *)(a1 + 24);
      EventActivityIdControl(4u, &ActivityId);
      v5 = *(_QWORD *)(a1 + 808);
      UserData.Ptr = *(_QWORD *)(a1 + 1216);
      v12 = a1 + 56;
      *(_QWORD *)&UserData.Size = 16;
      v10 = a1 + 24;
      v11 = 16;
      v13 = 16;
      v6 = *(_QWORD *)(v5 + 128);
      v15 = *(_DWORD *)(v5 + 148);
      v17 = v5;
      v14 = v6;
      v16 = 0;
      v18 = 16;
      EventWrite(g_hETW, a2, 5u, &UserData);
      EventActivityIdControl(2u, &ActivityId);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (__int64)L"DpspRaiseScenarioDispatchEvent",
      153,
      (const wchar_t *)L"Error = %d",
      87);
  }
  return v4;
}

```

## disassembly

```asm
0x180007694  mov     [rsp-8+arg_0], rbx
0x180007699  mov     [rsp-8+arg_10], rsi
0x18000769e  push    rbp
0x18000769f  push    rdi
0x1800076a0  push    r14
0x1800076a2  lea     rbp, [rsp-47h]
0x1800076a7  sub     rsp, 0A0h
0x1800076ae  mov     rax, cs:__security_cookie
0x1800076b5  xor     rax, rsp
0x1800076b8  mov     [rbp+57h+var_20], rax
0x1800076bc  mov     r14, rdx
0x1800076bf  mov     [rbp+57h+UserData.Ptr], 0
0x1800076c7  xor     edx, edx; Val
0x1800076c9  mov     rdi, rcx
0x1800076cc  xorps   xmm0, xmm0
0x1800076cf  lea     rcx, [rbp+57h+UserData.Size]; void *
0x1800076d3  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800076d7  lea     r8d, [rdx+48h]; Size
0x1800076db  call    memset_0
0x1800076e0  test    rdi, rdi
0x1800076e3  jnz     short loc_180007717
0x1800076e5  lea     r9, aErrorD; "Error = %d"
0x1800076ec  mov     dword ptr [rsp+0B0h+Args], 57h ; 'W'; Args
0x1800076f4  mov     r8d, 99h; int
0x1800076fa  lea     rdx, aDpspraisescena_0; "DpspRaiseScenarioDispatchEvent"
0x180007701  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007708  mov     esi, 80070057h
0x18000770d  call    WdipTraceError
0x180007712  jmp     loc_1800077D4
0x180007717  mov     rcx, cs:g_hETW; RegHandle
0x18000771e  mov     rdx, r14; EventDescriptor
0x180007721  xor     esi, esi
0x180007723  call    cs:__imp_EventEnabled
0x180007729  test    al, al
0x18000772b  jz      loc_1800077D4
0x180007731  lea     rbx, [rdi+18h]
0x180007735  test    rbx, rbx
0x180007738  jz      short loc_180007742
0x18000773a  movups  xmm0, xmmword ptr [rbx]
0x18000773d  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180007742  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180007746  mov     ecx, 4; ControlCode
0x18000774b  call    cs:__imp_EventActivityIdControl
0x180007751  mov     r8, [rdi+328h]
0x180007758  lea     r9, [rbp+57h+UserData]; UserData
0x18000775c  mov     rax, [rdi+4C0h]
0x180007763  mov     rdx, r14; EventDescriptor
0x180007766  mov     [rbp+57h+UserData.Ptr], rax
0x18000776a  lea     rax, [rdi+38h]
0x18000776e  mov     [rbp+57h+var_50], rax
0x180007772  mov     qword ptr [rbp+57h+UserData.Size], 10h
0x18000777a  mov     [rbp+57h+var_60], rbx
0x18000777e  mov     [rbp+57h+var_58], 10h
0x180007786  mov     [rbp+57h+var_48], 10h
0x18000778e  mov     ecx, [r8+94h]
0x180007795  mov     rax, [r8+80h]
0x18000779c  mov     [rbp+57h+var_38], ecx
0x18000779f  mov     rcx, cs:g_hETW; RegHandle
0x1800077a6  mov     [rbp+57h+var_30], r8
0x1800077aa  mov     r8d, 5; UserDataCount
0x1800077b0  mov     [rbp+57h+var_40], rax
0x1800077b4  mov     [rbp+57h+var_34], esi
0x1800077b7  mov     [rbp+57h+var_28], 10h
0x1800077bf  call    cs:__imp_EventWrite
0x1800077c5  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800077c9  mov     ecx, 2; ControlCode
0x1800077ce  call    cs:__imp_EventActivityIdControl
0x1800077d4  mov     eax, esi
0x1800077d6  mov     rcx, [rbp+57h+var_20]
0x1800077da  xor     rcx, rsp; StackCookie
0x1800077dd  call    __security_check_cookie
0x1800077e2  lea     r11, [rsp+0B0h+var_10]
0x1800077ea  mov     rbx, [r11+20h]
0x1800077ee  mov     rsi, [r11+30h]
0x1800077f2  mov     rsp, r11
0x1800077f5  pop     r14
0x1800077f7  pop     rdi
0x1800077f8  pop     rbp
0x1800077f9  retn
```
