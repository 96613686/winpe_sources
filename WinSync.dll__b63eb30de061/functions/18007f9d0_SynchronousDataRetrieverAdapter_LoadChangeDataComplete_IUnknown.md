# SynchronousDataRetrieverAdapter::LoadChangeDataComplete(IUnknown *)

- ea: `0x18007f9d0`
- end: `0x18007fa8e`
- name: `?LoadChangeDataComplete@SynchronousDataRetrieverAdapter@@UEAAJPEAUIUnknown@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(SynchronousDataRetrieverAdapter *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180047300`
- `0x18007f9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa36`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007fa2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007fa2c`

## string_xrefs

- `0x18007fa02`: `SynchronousDataRetrieverAdapter::LoadChangeDataComplete`
- `0x18007fa67`: `SynchronousDataRetrieverAdapter::LoadChangeDataComplete`

## pseudocode

```c
__int64 __fastcall SynchronousDataRetrieverAdapter::LoadChangeDataComplete(HANDLE *this, struct IUnknown *a2)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids,
      "SynchronousDataRetrieverAdapter::LoadChangeDataComplete");
  }
  v4 = 0;
  SharedRefPtr<IUnknown>::AttachExternal(this + 5, a2);
  if ( !SetEvent(this[6]) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids,
      (unsigned int)"SynchronousDataRetrieverAdapter::LoadChangeDataComplete",
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18007f9d0  push    rbx
0x18007f9d2  push    rbp
0x18007f9d3  push    rsi
0x18007f9d4  push    rdi
0x18007f9d5  sub     rsp, 38h
0x18007f9d9  mov     rsi, rdx
0x18007f9dc  mov     rdi, rcx
0x18007f9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f9e6  lea     rbp, WPP_GLOBAL_Control
0x18007f9ed  cmp     rcx, rbp
0x18007f9f0  jz      short loc_18007FA1A
0x18007f9f2  test    byte ptr [rcx+1Ch], 80h
0x18007f9f6  jz      short loc_18007FA1A
0x18007f9f8  cmp     byte ptr [rcx+19h], 5
0x18007f9fc  jb      short loc_18007FA1A
0x18007f9fe  mov     rcx, [rcx+10h]
0x18007fa02  lea     r9, aSynchronousdat_2; "SynchronousDataRetrieverAdapter::LoadCh"...
0x18007fa09  mov     edx, 10h
0x18007fa0e  lea     r8, WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids
0x18007fa15  call    WPP_SF_s
0x18007fa1a  lea     rcx, [rdi+28h]
0x18007fa1e  mov     rdx, rsi
0x18007fa21  xor     ebx, ebx
0x18007fa23  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18007fa28  mov     rcx, [rdi+30h]; hEvent
0x18007fa2c  call    cs:__imp_SetEvent
0x18007fa32  test    eax, eax
0x18007fa34  jnz     short loc_18007FA4B
0x18007fa36  call    cs:__imp_GetLastError
0x18007fa3c  mov     ebx, eax
0x18007fa3e  test    eax, eax
0x18007fa40  jle     short loc_18007FA4B
0x18007fa42  movzx   ebx, ax
0x18007fa45  or      ebx, 80070000h
0x18007fa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fa52  cmp     rcx, rbp
0x18007fa55  jz      short loc_18007FA83
0x18007fa57  test    byte ptr [rcx+1Ch], 80h
0x18007fa5b  jz      short loc_18007FA83
0x18007fa5d  cmp     byte ptr [rcx+19h], 5
0x18007fa61  jb      short loc_18007FA83
0x18007fa63  mov     rcx, [rcx+10h]
0x18007fa67  lea     r9, aSynchronousdat_2; "SynchronousDataRetrieverAdapter::LoadCh"...
0x18007fa6e  mov     edx, 11h
0x18007fa73  mov     [rsp+58h+var_38], ebx
0x18007fa77  lea     r8, WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids
0x18007fa7e  call    WPP_SF_sD
0x18007fa83  mov     eax, ebx
0x18007fa85  add     rsp, 38h
0x18007fa89  pop     rdi
0x18007fa8a  pop     rsi
0x18007fa8b  pop     rbp
0x18007fa8c  pop     rbx
0x18007fa8d  retn
```
