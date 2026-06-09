# ShieldProvider::ShieldConfigStorageManager::IsDefenderSvcPresent(void)

- ea: `0x180087624`
- end: `0x1800876a2`
- name: `?IsDefenderSvcPresent@ShieldConfigStorageManager@ShieldProvider@@AEAA_NXZ`
- size: `126`
- prototype: `bool(ShieldProvider::ShieldConfigStorageManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180087350`

## callees

- `0x180087624`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180087680`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180087693`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180087680`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180087693`

## pseudocode

```c
bool __fastcall ShieldProvider::ShieldConfigStorageManager::IsDefenderSvcPresent(
        ShieldProvider::ShieldConfigStorageManager *this,
        struct SC_HANDLE__ **a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  bool v4; // di
  const unsigned __int16 *v6; // [rsp+20h] [rbp-8h]
  unsigned int v7; // [rsp+20h] [rbp-8h]
  SC_HANDLE v8; // [rsp+30h] [rbp+8h] BYREF
  SC_HANDLE hSCObject; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v4 = 0;
  if ( (int)CommonUtil::HrOpenSCManager((CommonUtil *)&v8, a2, a3, a4, v6) >= 0 )
  {
    hSCObject = 0;
    v4 = CommonUtil::HrOpenService(
           (CommonUtil *)&hSCObject,
           (struct SC_HANDLE__ **)v8,
           (struct SC_HANDLE__ *)&stru_1800FE5B8,
           (const unsigned __int16 *)4,
           v7) >= 0;
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
  }
  if ( v8 )
    CloseServiceHandle(v8);
  return v4;
}

```

## disassembly

```asm
0x180087624  mov     [rsp+arg_0], rcx
0x180087629  push    rdi; unsigned int
0x18008762a  sub     rsp, 20h
0x18008762e  lea     rcx, [rsp+28h+arg_0]; this
0x180087633  mov     [rsp+28h+arg_0], 0
0x18008763c  xor     dil, dil
0x18008763f  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x180087644  test    eax, eax
0x180087646  js      short loc_180087686
0x180087648  mov     rdx, [rsp+28h+arg_0]; struct SC_HANDLE__ **
0x18008764d  lea     r8, stru_1800FE5B8; struct SC_HANDLE__ *
0x180087654  mov     r9d, 4; unsigned __int16 *
0x18008765a  mov     [rsp+28h+hSCObject], 0
0x180087663  lea     rcx, [rsp+28h+hSCObject]; this
0x180087668  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18008766d  mov     rcx, [rsp+28h+hSCObject]; hSCObject
0x180087672  mov     edi, eax
0x180087674  shr     edi, 1Fh
0x180087677  xor     dil, 1
0x18008767b  test    rcx, rcx
0x18008767e  jz      short loc_180087686
0x180087680  call    cs:__imp_CloseServiceHandle
0x180087686  cmp     [rsp+28h+arg_0], 0
0x18008768c  jz      short loc_180087699
0x18008768e  mov     rcx, [rsp+28h+arg_0]; hSCObject
0x180087693  call    cs:__imp_CloseServiceHandle
0x180087699  mov     al, dil
0x18008769c  add     rsp, 20h
0x1800876a0  pop     rdi
0x1800876a1  retn
```
