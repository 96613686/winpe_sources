# UsbDevice_SetResourceAssignmentCompletion

- ea: `0x140035c70`
- end: `0x140035d42`
- name: `UsbDevice_SetResourceAssignmentCompletion`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001bb78`
- `0x14002ff50`
- `0x140035c70`
- `0x140035d48`
- `0x1400412a4`

## string_xrefs

- `0x140035cc7`: `Endpoint is already offloaded`

## pseudocode

```c
__int64 __fastcall UsbDevice_SetResourceAssignmentCompletion(__int64 a1, __int64 a2)
{
  __int64 *v2; // rdi
  __int64 v3; // rbx
  __int64 result; // rax
  int v5; // ecx
  __int64 v6; // rcx
  int v7; // edx

  v2 = *(__int64 **)(a1 + 48);
  v3 = v2[2];
  --*(_DWORD *)(v3 + 588);
  if ( *(_BYTE *)(a1 + 60) == 1 )
  {
    if ( *(_DWORD *)(v3 + 608) == 8 )
    {
      v5 = *((_DWORD *)v2 + 344);
      if ( v5 == 2 )
      {
        result = Debug_FreAssertMsg(
                   "Endpoint is already offloaded",
                   0,
                   "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\endpoint.h",
                   1382);
      }
      else
      {
        if ( *(_DWORD *)(*v2 + 1084) == 2 )
        {
          LOBYTE(a2) = v5 == 1;
          Debug_FreAssertMsg(
            "Invalid current offload state",
            a2,
            "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\endpoint.h",
            1389);
        }
        v6 = *v2;
        *((_DWORD *)v2 + 344) = 2;
        result = Controller_IncrementNumberOfEndpointsOffloaded(v6);
      }
    }
  }
  else
  {
    result = UsbDevice_SetConfigureRequestStatus(v3, 3221225473LL);
    *(_BYTE *)(v3 + 592) = 1;
  }
  if ( !*(_DWORD *)(v3 + 588) )
  {
    v7 = 1;
    if ( *(_BYTE *)(v3 + 592) )
      v7 = 2;
    return UsbDevice_QueueConfigureEndpointEvent(v3, v7);
  }
  return result;
}

```

## disassembly

```asm
0x140035c70  mov     [rsp+arg_0], rbx
0x140035c75  push    rdi
0x140035c76  sub     rsp, 20h
0x140035c7a  mov     rdi, [rcx+30h]
0x140035c7e  mov     rbx, [rdi+10h]
0x140035c82  dec     dword ptr [rbx+24Ch]
0x140035c88  cmp     byte ptr [rcx+3Ch], 1
0x140035c8c  jz      short loc_140035CA4
0x140035c8e  mov     edx, 0C0000001h
0x140035c93  mov     rcx, rbx
0x140035c96  call    UsbDevice_SetConfigureRequestStatus
0x140035c9b  mov     byte ptr [rbx+250h], 1
0x140035ca2  jmp     short loc_140035D12
0x140035ca4  cmp     dword ptr [rbx+260h], 8
0x140035cab  jnz     short loc_140035D12
0x140035cad  mov     ecx, [rdi+560h]
0x140035cb3  cmp     ecx, 2
0x140035cb6  jnz     short loc_140035CD5
0x140035cb8  mov     r9d, 566h
0x140035cbe  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140035cc5  xor     edx, edx
0x140035cc7  lea     rcx, aEndpointIsAlre; "Endpoint is already offloaded"
0x140035cce  call    Debug_FreAssertMsg
0x140035cd3  jmp     short loc_140035D12
0x140035cd5  mov     rax, [rdi]
0x140035cd8  cmp     dword ptr [rax+43Ch], 2
0x140035cdf  jnz     short loc_140035D00
0x140035ce1  cmp     ecx, 1
0x140035ce4  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140035ceb  mov     r9d, 56Dh
0x140035cf1  lea     rcx, aInvalidCurrent; "Invalid current offload state"
0x140035cf8  setz    dl
0x140035cfb  call    Debug_FreAssertMsg
0x140035d00  mov     rcx, [rdi]
0x140035d03  mov     dword ptr [rdi+560h], 2
0x140035d0d  call    Controller_IncrementNumberOfEndpointsOffloaded
0x140035d12  cmp     dword ptr [rbx+24Ch], 0
0x140035d19  jnz     short loc_140035D36
0x140035d1b  cmp     byte ptr [rbx+250h], 0
0x140035d22  mov     rcx, rbx
0x140035d25  mov     edx, 1
0x140035d2a  jz      short loc_140035D31
0x140035d2c  mov     edx, 2
0x140035d31  call    UsbDevice_QueueConfigureEndpointEvent
0x140035d36  mov     rbx, [rsp+28h+arg_0]
0x140035d3b  add     rsp, 20h
0x140035d3f  pop     rdi
0x140035d40  retn
```
