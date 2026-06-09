# DeviceAttributes::GetServicingTrain(ushort * *)

- ea: `0x180010420`
- end: `0x1800104b3`
- name: `?GetServicingTrain@DeviceAttributes@@UEAAJPEAPEAG@Z`
- size: `147`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006e28`
- `0x180010420`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104a5`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetServicingTrain(DeviceAttributes *this, unsigned __int16 **a2)
{
  __int64 v2; // rax
  wchar_t *v4; // rdx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_QWORD *)this;
  v6 = 0;
  v7 = 0;
  if ( (*(int (__fastcall **)(DeviceAttributes *, int *))(v2 + 24))(this, &v6) < 0 )
  {
    v4 = L"Invalid";
    goto LABEL_11;
  }
  switch ( v6 )
  {
    case 0:
      v4 = L"AB";
      goto LABEL_11;
    case 1:
      v4 = L"CB";
      goto LABEL_11;
    case 2:
      v4 = L"CBB";
      goto LABEL_11;
    case 3:
      v4 = L"LTSB";
LABEL_11:
      CSpDynamicString::operator=((LPVOID *)&v7, v4);
      break;
  }
  *a2 = v7;
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x180010420  push    rbx
0x180010422  sub     rsp, 20h
0x180010426  mov     rax, [rcx]
0x180010429  mov     rbx, rdx
0x18001042c  lea     rdx, [rsp+28h+arg_0]
0x180010431  mov     [rsp+28h+arg_0], 0
0x180010439  mov     [rsp+28h+arg_8], 0
0x180010442  mov     rax, [rax+18h]
0x180010446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001044b  test    eax, eax
0x18001044d  js      short loc_18001048A
0x18001044f  mov     ecx, [rsp+28h+arg_0]
0x180010453  test    ecx, ecx
0x180010455  jz      short loc_180010481
0x180010457  sub     ecx, 1
0x18001045a  jz      short loc_180010478
0x18001045c  sub     ecx, 1
0x18001045f  jz      short loc_18001046F
0x180010461  cmp     ecx, 1
0x180010464  jnz     short loc_18001049B
0x180010466  lea     rdx, aLtsb; "LTSB"
0x18001046d  jmp     short loc_180010491
0x18001046f  lea     rdx, aCbb; "CBB"
0x180010476  jmp     short loc_180010491
0x180010478  lea     rdx, aCb; "CB"
0x18001047f  jmp     short loc_180010491
0x180010481  lea     rdx, aAb; "AB"
0x180010488  jmp     short loc_180010491
0x18001048a  lea     rdx, aInvalid; "Invalid"
0x180010491  lea     rcx, [rsp+28h+arg_8]
0x180010496  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18001049b  mov     rax, [rsp+28h+arg_8]
0x1800104a0  xor     ecx, ecx; pv
0x1800104a2  mov     [rbx], rax
0x1800104a5  call    cs:__imp_CoTaskMemFree
0x1800104ab  xor     eax, eax
0x1800104ad  add     rsp, 20h
0x1800104b1  pop     rbx
0x1800104b2  retn
```
