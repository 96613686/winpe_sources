# DpspSendASyncMessage(_DPS_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,ulong,void *,ushort)

- ea: `0x180011b88`
- end: `0x180011c66`
- name: `?DpspSendASyncMessage@@YAJPEAU_DPS_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@KPEAXG@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct _DPS_MESSAGE *, struct _ALPC_MESSAGE_ATTRIBUTES *, unsigned int, void *, unsigned __int16)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001100`
- `0x1800057b0`
- `0x1800065b8`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011eec`
- `0x180011fd4`

## callees

- `0x180009090`
- `0x180011b88`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011c1e`
- `ntdll!RtlNtStatusToDosError` at `0x180011c1e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180011c0e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180011c0e`

## pseudocode

```c
__int64 __fastcall DpspSendASyncMessage(
        struct _DPS_MESSAGE *a1,
        struct _ALPC_MESSAGE_ATTRIBUTES *a2,
        unsigned int a3,
        void *a4,
        unsigned __int16 a5)
{
  unsigned int v5; // ebx
  int v6; // r8d
  NTSTATUS v7; // eax
  signed int v8; // eax
  char Args[8]; // [rsp+20h] [rbp-28h]

  if ( !a1 )
  {
    v5 = -2147024809;
    *(_DWORD *)Args = 87;
    v6 = 50;
LABEL_9:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
      (__int64)L"DpspSendASyncMessage",
      v6,
      (const wchar_t *)L"Error = %d",
      *(_QWORD *)Args);
    return v5;
  }
  *((_DWORD *)a1 + 6) = 0;
  *((_DWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_WORD *)a1 + 1) = a5;
  *(_WORD *)a1 = a5 - 40;
  v7 = NtAlpcSendWaitReceivePort(a4, a3, a1, a2, 0, 0, 0, 0);
  if ( v7 < 0 )
  {
    v8 = RtlNtStatusToDosError(v7);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    v5 = 0;
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 71;
    *(_DWORD *)Args = (unsigned __int16)v5;
    goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x180011b88  push    rbx
0x180011b8a  sub     rsp, 40h
0x180011b8e  mov     r11d, r8d
0x180011b91  mov     r8, rcx
0x180011b94  mov     r10, r9
0x180011b97  test    rcx, rcx
0x180011b9a  jnz     short loc_180011BB2
0x180011b9c  mov     ebx, 80070057h
0x180011ba1  mov     dword ptr [rsp+48h+Args], 57h ; 'W'
0x180011ba9  lea     r8d, [rcx+32h]
0x180011bad  jmp     loc_180011C44
0x180011bb2  mov     dword ptr [rcx+18h], 0
0x180011bb9  mov     r9, rdx
0x180011bbc  mov     dword ptr [rcx+4], 0
0x180011bc3  mov     edx, r11d
0x180011bc6  mov     qword ptr [rcx+8], 0
0x180011bce  mov     qword ptr [rcx+10h], 0
0x180011bd6  movzx   ecx, [rsp+48h+arg_20]
0x180011bdb  mov     [rsp+48h+var_10], 0
0x180011be4  mov     [r8+2], cx
0x180011be9  mov     [rsp+48h+var_18], 0
0x180011bf2  lea     eax, [rcx-28h]
0x180011bf5  mov     [rsp+48h+var_20], 0
0x180011bfe  mov     rcx, r10
0x180011c01  mov     [r8], ax
0x180011c05  mov     qword ptr [rsp+48h+Args], 0
0x180011c0e  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180011c14  test    eax, eax
0x180011c16  js      short loc_180011C1C
0x180011c18  xor     ebx, ebx
0x180011c1a  jmp     short loc_180011C33
0x180011c1c  mov     ecx, eax; Status
0x180011c1e  call    cs:__imp_RtlNtStatusToDosError
0x180011c24  mov     ebx, eax
0x180011c26  test    eax, eax
0x180011c28  jle     short loc_180011C33
0x180011c2a  movzx   ebx, ax
0x180011c2d  or      ebx, 80070000h
0x180011c33  test    ebx, ebx
0x180011c35  jns     short loc_180011C5E
0x180011c37  movzx   ecx, bx
0x180011c3a  mov     r8d, 47h ; 'G'; int
0x180011c40  mov     dword ptr [rsp+48h+Args], ecx; Args
0x180011c44  lea     r9, aErrorD; "Error = %d"
0x180011c4b  lea     rdx, aDpspsendasyncm; "DpspSendASyncMessage"
0x180011c52  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180011c59  call    WdipTraceError
0x180011c5e  mov     eax, ebx
0x180011c60  add     rsp, 40h
0x180011c64  pop     rbx
0x180011c65  retn
```
