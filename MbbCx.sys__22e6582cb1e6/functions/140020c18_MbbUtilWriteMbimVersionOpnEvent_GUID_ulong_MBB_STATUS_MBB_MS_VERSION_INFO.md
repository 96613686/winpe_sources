# MbbUtilWriteMbimVersionOpnEvent(_GUID *,ulong,_MBB_STATUS,_MBB_MS_VERSION_INFO *)

- ea: `0x140020c18`
- end: `0x140020d3a`
- name: `?MbbUtilWriteMbimVersionOpnEvent@@YAXPEAU_GUID@@KW4_MBB_STATUS@@PEAU_MBB_MS_VERSION_INFO@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fa30`
- `0x14001db50`

## callees

- `0x140024338`
- `0x140047e50`

## pseudocode

```c
void __fastcall MbbUtilWriteMbimVersionOpnEvent(const GUID *a1, int a2, __int64 a3, __int64 a4)
{
  int v4; // [rsp+C0h] [rbp-88h]
  int v5[4]; // [rsp+C8h] [rbp-80h] BYREF
  _DWORD v6[4]; // [rsp+D8h] [rbp-70h] BYREF
  int v7; // [rsp+E8h] [rbp-60h] BYREF
  int v8; // [rsp+ECh] [rbp-5Ch] BYREF
  int v9; // [rsp+F0h] [rbp-58h] BYREF
  int v10; // [rsp+F8h] [rbp-50h] BYREF
  int v11; // [rsp+100h] [rbp-48h] BYREF
  int v12; // [rsp+104h] [rbp-44h] BYREF
  struct _GUID v13; // [rsp+108h] [rbp-40h] BYREF

  v10 = a2;
  v4 = 4;
  v5[0] = 4;
  v6[0] = 0;
  v13 = MBB_UUID_BASIC_CONNECT_EXTENSIONS;
  v7 = 15;
  v12 = -2147483645;
  v11 = 52;
  v9 = 1;
  v8 = 0;
  MbbWriteEventOpn(
    &COMMAND_DONE_MSG,
    a1,
    0,
    0xAu,
    &v12,
    4,
    &v11,
    4,
    &v10,
    4,
    &v9,
    4,
    &v8,
    4,
    &v13,
    16,
    &v7,
    4,
    v6,
    4,
    v5,
    4,
    a4,
    v4);
}

```

## disassembly

```asm
0x140020c18  mov     r11, rsp
0x140020c1b  push    rbp
0x140020c1c  lea     rbp, [r11+18h]
0x140020c20  sub     rsp, 120h
0x140020c27  mov     rax, cs:__security_cookie
0x140020c2e  xor     rax, rsp
0x140020c31  mov     [rbp-20h+var_10], rax
0x140020c35  movups  xmm0, xmmword ptr cs:MBB_UUID_BASIC_CONNECT_EXTENSIONS.Data1
0x140020c3c  mov     r8d, 4
0x140020c42  mov     [rbp-20h+var_30], edx
0x140020c45  mov     [r11-70h], r8d
0x140020c49  lea     rax, [rbp-20h+var_60]
0x140020c4d  mov     [r11-78h], r9
0x140020c51  mov     [r11-80h], r8
0x140020c55  mov     [r11-88h], rax
0x140020c5c  lea     edx, [r8+6]
0x140020c60  mov     [r11-90h], r8
0x140020c67  lea     rax, [rbp-20h+var_50]
0x140020c6b  mov     [r11-98h], rax
0x140020c72  mov     r9d, edx; unsigned __int16
0x140020c75  mov     [r11-0A0h], r8
0x140020c7c  lea     rax, [rbp-20h+var_40]
0x140020c80  mov     [r11-0A8h], rax
0x140020c87  mov     rdx, rcx; ActivityId
0x140020c8a  mov     qword ptr [rsp+78h], 10h
0x140020c93  lea     rax, [rbp-20h+var_20]
0x140020c97  mov     [rsp+120h+var_B0], rax
0x140020c9c  lea     rcx, COMMAND_DONE_MSG; EventDescriptor
0x140020ca3  mov     [rsp+120h+var_B8], r8
0x140020ca8  lea     rax, [rbp-20h+var_3C]
0x140020cac  mov     [rsp+120h+var_C0], rax
0x140020cb1  lea     rax, [rbp-20h+var_38]
0x140020cb5  mov     [rsp+120h+var_C8], r8
0x140020cba  mov     [rsp+120h+var_D0], rax
0x140020cbf  lea     rax, [rbp-20h+var_30]
0x140020cc3  mov     [rsp+120h+var_D8], r8
0x140020cc8  mov     [rsp+120h+var_E0], rax
0x140020ccd  lea     rax, [rbp-20h+var_28]
0x140020cd1  mov     [rsp+120h+var_E8], r8
0x140020cd6  mov     [rsp+120h+var_F0], rax
0x140020cdb  lea     rax, [rbp-20h+var_24]
0x140020cdf  mov     [rsp+120h+var_F8], r8
0x140020ce4  mov     [rbp-20h+var_60], r8d
0x140020ce8  xor     r8d, r8d; RelatedActivityId
0x140020ceb  mov     [rsp+120h+var_100], rax
0x140020cf0  mov     [rbp-20h+var_50], 0
0x140020cf7  movdqu  [rbp-20h+var_20], xmm0
0x140020cfc  mov     [rbp-20h+var_40], 0Fh
0x140020d03  mov     [rbp-20h+var_24], 80000003h
0x140020d0a  mov     [rbp-20h+var_28], 34h ; '4'
0x140020d11  mov     [rbp-20h+var_38], 1
0x140020d18  mov     [rbp-20h+var_3C], 0
0x140020d1f  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x140020d24  mov     rcx, [rbp-20h+var_10]
0x140020d28  xor     rcx, rsp; StackCookie
0x140020d2b  call    __security_check_cookie
0x140020d30  add     rsp, 120h
0x140020d37  pop     rbp
0x140020d38  retn
```
