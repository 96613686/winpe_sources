# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)

- ea: `0x180022d0c`
- end: `0x180022d6c`
- name: `?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z`
- size: `96`
- prototype: `int(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *, struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800237e8`
- `0x1800248ac`
- `0x180024e1c`
- `0x180025e24`

## callees

- `0x180022d0c`
- `0x180025724`
- `0x180026390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022d59`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
        Microsoft::Bluetooth::Services::BthServ **this,
        struct _BLUETOOTH_SDP_RECORD *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  unsigned int v4; // edi
  Microsoft::Bluetooth::Services::BthServ *v6; // rcx
  void *v7; // r8
  DWORD v8; // ecx

  v4 = 0;
  if ( !this )
  {
    v8 = 6;
    goto LABEL_8;
  }
  v6 = *this;
  if ( !v6 || v6 >= this[1] )
  {
    v8 = 259;
LABEL_8:
    SetLastError(v8);
    return v4;
  }
  v4 = Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(v6, a2, a2, a4);
  if ( v4 )
    *this = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(*this, this[1], v7);
  return v4;
}

```

## disassembly

```asm
0x180022d0c  mov     [rsp+arg_0], rbx
0x180022d11  push    rdi
0x180022d12  sub     rsp, 20h
0x180022d16  xor     edi, edi
0x180022d18  mov     rbx, rcx
0x180022d1b  test    rcx, rcx
0x180022d1e  jz      short loc_180022D54
0x180022d20  mov     rcx, [rcx]; this
0x180022d23  test    rcx, rcx
0x180022d26  jz      short loc_180022D4D
0x180022d28  cmp     rcx, [rbx+8]
0x180022d2c  jnb     short loc_180022D4D
0x180022d2e  mov     r8, rdx; void *
0x180022d31  call    ?BthpTransposeToUUID@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(_BLUETOOTH_SDP_RECORD *,void *,_GUID *)
0x180022d36  mov     edi, eax
0x180022d38  test    eax, eax
0x180022d3a  jz      short loc_180022D5F
0x180022d3c  mov     rdx, [rbx+8]; struct _BLUETOOTH_SDP_RECORD *
0x180022d40  mov     rcx, [rbx]; this
0x180022d43  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180022d48  mov     [rbx], rax
0x180022d4b  jmp     short loc_180022D5F
0x180022d4d  mov     ecx, 103h
0x180022d52  jmp     short loc_180022D59
0x180022d54  mov     ecx, 6; dwErrCode
0x180022d59  call    cs:__imp_SetLastError
0x180022d5f  mov     rbx, [rsp+28h+arg_0]
0x180022d64  mov     eax, edi
0x180022d66  add     rsp, 20h
0x180022d6a  pop     rdi
0x180022d6b  retn
```
