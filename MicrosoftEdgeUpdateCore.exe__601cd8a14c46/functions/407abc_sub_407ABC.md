# sub_407ABC

- ea: `0x407abc`
- end: `0x407b9e`
- name: `sub_407ABC`
- size: `226`
- prototype: `bool __thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x407a09`

## callees

- `0x4015d2`
- `0x401cac`
- `0x402488`
- `0x4042c0`
- `0x4043e2`
- `0x404782`
- `0x405f34`
- `0x40654c`
- `0x407abc`
- `0x408194`
- `0x40d08d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x407b64`
- `KERNEL32!GetLastError` at `0x407b64`

## string_xrefs

- `0x407ad0`: `_Microsoft_EdgeUpdate_logging_mutex_`

## pseudocode

```c
bool __thiscall sub_407ABC(_DWORD *this)
{
  int v2; // eax
  void **v3; // eax
  bool v4; // bl
  int v5; // ecx
  int v6; // ecx
  HANDLE v7; // eax
  int v9; // [esp-4h] [ebp-3Ch]
  int v10; // [esp+10h] [ebp-28h]
  int v11; // [esp+14h] [ebp-24h] BYREF
  _SECURITY_ATTRIBUTES MutexAttributes; // [esp+18h] [ebp-20h] BYREF
  void *v13[2]; // [esp+24h] [ebp-14h] BYREF
  int (__thiscall **v14)(void *, char); // [esp+2Ch] [ebp-Ch] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [esp+30h] [ebp-8h]

  v2 = sub_408194(this + 5);
  v3 = (void **)sub_40654C(&v11, v2);
  sub_401CAC(this + 3, v3);
  sub_4015D2((volatile signed __int32 *)(v11 - 16));
  sub_4015D2((volatile signed __int32 *)(v10 - 16));
  v4 = 0;
  v14 = &off_437C5C;
  pSecurityDescriptor = 0;
  sub_404782(v5);
  v6 = v9;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  v13[0] = &off_437C5C;
  v13[1] = 0;
  if ( pSecurityDescriptor )
    sub_402488(v13, pSecurityDescriptor);
  sub_4043E2(v13, v6);
  v7 = sub_405F34((LPCWSTR)this[3], &MutexAttributes);
  this[4] = v7;
  if ( v7 )
    v4 = GetLastError() == 183;
  v13[0] = &off_437C5C;
  sub_4042C0(v13);
  v14 = &off_437C5C;
  sub_4042C0((PSECURITY_DESCRIPTOR *)&v14);
  return v4;
}

```

## disassembly

```asm
0x407abc  push    ebp
0x407abd  mov     ebp, esp
0x407abf  sub     esp, 2Ch
0x407ac2  mov     eax, ___security_cookie
0x407ac7  xor     eax, ebp
0x407ac9  mov     [ebp+var_4], eax
0x407acc  push    ebx
0x407acd  push    esi
0x407ace  mov     esi, ecx
0x407ad0  mov     edx, offset aMicrosoftEdgeu_0; "_Microsoft_EdgeUpdate_logging_mutex_"
0x407ad5  push    edi
0x407ad6  lea     ecx, [ebp+var_28]
0x407ad9  lea     eax, [esi+14h]
0x407adc  push    eax
0x407add  call    sub_408194
0x407ae2  pop     ecx
0x407ae3  mov     edx, eax
0x407ae5  lea     ecx, [ebp+var_24]
0x407ae8  call    sub_40654C
0x407aed  push    eax
0x407aee  lea     ecx, [esi+0Ch]
0x407af1  call    sub_401CAC
0x407af6  mov     ecx, [ebp+var_24]
0x407af9  lea     ecx, [ecx-10h]
0x407afc  call    sub_4015D2
0x407b01  mov     ecx, [ebp+var_28]
0x407b04  add     ecx, 0FFFFFFF0h
0x407b07  call    sub_4015D2
0x407b0c  push    ecx
0x407b0d  xor     ebx, ebx
0x407b0f  mov     [ebp+var_C], offset off_437C5C
0x407b16  lea     ecx, [ebp+var_C]
0x407b19  mov     [ebp+pSecurityDescriptor], ebx
0x407b1c  call    sub_404782
0x407b21  pop     ecx
0x407b22  mov     [ebp+MutexAttributes.nLength], ebx
0x407b25  mov     [ebp+MutexAttributes.lpSecurityDescriptor], ebx
0x407b28  mov     [ebp+MutexAttributes.bInheritHandle], ebx
0x407b2b  mov     [ebp+var_14], offset off_437C5C
0x407b32  mov     [ebp+var_10], ebx
0x407b35  cmp     [ebp+pSecurityDescriptor], ebx
0x407b38  jz      short loc_407B45
0x407b3a  push    [ebp+pSecurityDescriptor]; pSecurityDescriptor
0x407b3d  lea     ecx, [ebp+var_14]
0x407b40  call    sub_402488
0x407b45  push    ecx
0x407b46  lea     eax, [ebp+var_14]
0x407b49  push    eax
0x407b4a  lea     ecx, [ebp+MutexAttributes]
0x407b4d  call    sub_4043E2
0x407b52  mov     ecx, [esi+0Ch]; lpName
0x407b55  lea     edx, [ebp+MutexAttributes]; lpMutexAttributes
0x407b58  call    sub_405F34
0x407b5d  mov     [esi+10h], eax
0x407b60  test    eax, eax
0x407b62  jz      short loc_407B72
0x407b64  call    ds:GetLastError
0x407b6a  cmp     eax, 0B7h
0x407b6f  setz    bl
0x407b72  mov     esi, offset off_437C5C
0x407b77  lea     ecx, [ebp+var_14]
0x407b7a  mov     [ebp+var_14], esi
0x407b7d  call    sub_4042C0
0x407b82  lea     ecx, [ebp+var_C]
0x407b85  mov     [ebp+var_C], esi
0x407b88  call    sub_4042C0
0x407b8d  mov     ecx, [ebp+var_4]
0x407b90  mov     al, bl
0x407b92  pop     edi
0x407b93  pop     esi
0x407b94  xor     ecx, ebp; StackCookie
0x407b96  pop     ebx
0x407b97  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407b9c  leave
0x407b9d  retn
```
