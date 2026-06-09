# Apx::ApfDevice::SwCreateApxRootContainerCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180010380`
- end: `0x180010429`
- name: `?SwCreateApxRootContainerCallback@ApfDevice@Apx@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `169`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, HANDLE *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a12c`
- `0x180010380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800103ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800103ed`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x1800103d8`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x1800103d8`

## pseudocode

```c
void __fastcall Apx::ApfDevice::SwCreateApxRootContainerCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        HANDLE *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rcx

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 >= 0 )
  {
    SwDeviceSetLifetime(a1, 1, a3, a4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    SetEvent(*a3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_(v7[2], 35, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
}

```

## disassembly

```asm
0x180010380  push    rbx
0x180010382  push    rbp
0x180010383  push    rsi
0x180010384  push    rdi
0x180010385  sub     rsp, 28h
0x180010389  mov     rbx, r8
0x18001038c  mov     edi, edx
0x18001038e  mov     rsi, rcx
0x180010391  mov     rcx, cs:WPP_GLOBAL_Control
0x180010398  lea     rbp, WPP_GLOBAL_Control
0x18001039f  cmp     rcx, rbp
0x1800103a2  jz      short loc_1800103CC
0x1800103a4  test    byte ptr [rcx+1Ch], 1
0x1800103a8  jz      short loc_1800103CC
0x1800103aa  cmp     byte ptr [rcx+19h], 5
0x1800103ae  jb      short loc_1800103CC
0x1800103b0  mov     rcx, [rcx+10h]
0x1800103b4  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x1800103bb  mov     edx, 22h ; '"'
0x1800103c0  call    WPP_SF_
0x1800103c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103cc  test    edi, edi
0x1800103ce  js      short loc_1800103E5
0x1800103d0  mov     edx, 1
0x1800103d5  mov     rcx, rsi
0x1800103d8  call    cs:__imp_SwDeviceSetLifetime
0x1800103de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103e5  test    rbx, rbx
0x1800103e8  jz      short loc_1800103FA
0x1800103ea  mov     rcx, [rbx]; hEvent
0x1800103ed  call    cs:__imp_SetEvent
0x1800103f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103fa  cmp     rcx, rbp
0x1800103fd  jz      short loc_180010420
0x1800103ff  test    byte ptr [rcx+1Ch], 1
0x180010403  jz      short loc_180010420
0x180010405  cmp     byte ptr [rcx+19h], 5
0x180010409  jb      short loc_180010420
0x18001040b  mov     rcx, [rcx+10h]
0x18001040f  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x180010416  mov     edx, 23h ; '#'
0x18001041b  call    WPP_SF_
0x180010420  add     rsp, 28h
0x180010424  pop     rdi
0x180010425  pop     rsi
0x180010426  pop     rbp
0x180010427  pop     rbx
0x180010428  retn
```
