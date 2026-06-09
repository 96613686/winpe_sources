# CIEAdminBrokerObject::QueryInterface(_GUID const &,void * *)

- ea: `0x405a60`
- end: `0x405b78`
- name: `?QueryInterface@CIEAdminBrokerObject@@UAGJABU_GUID@@PAPAX@Z`
- size: `280`
- prototype: `int __stdcall(CIEAdminBrokerObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4061a0`
- `0x4061b0`

## callees

- `0x405a60`
- `0x4081a5`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::QueryInterface(CIEAdminBrokerObject *this, const struct _GUID *a2, void **a3)
{
  int v3; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  char *v7; // eax
  int i; // ecx
  int j; // ecx

  v3 = 0;
  v4 = 0;
  while ( *(&a2->Data1 + v4) == *(&IID_IUnknown.Data1 + v4) )
  {
    if ( ++v4 == 4 )
    {
LABEL_12:
      v7 = (char *)this + 8;
LABEL_13:
      *a3 = this != 0 ? v7 : 0;
LABEL_14:
      (*(void (__thiscall **)(_DWORD, CIEAdminBrokerObject *))(*(_DWORD *)this + 4))(
        *(_DWORD *)(*(_DWORD *)this + 4),
        this);
      return v3;
    }
  }
  v5 = 0;
  while ( *(&a2->Data1 + v5) == *(&IID_IeAxiInstaller.Data1 + v5) )
  {
    if ( ++v5 == 4 )
      goto LABEL_12;
  }
  v6 = 0;
  while ( *(&a2->Data1 + v6) == *(&IID_IeAxiInstaller2.Data1 + v6) )
  {
    if ( ++v6 == 4 )
      goto LABEL_12;
  }
  for ( i = 0; i != 4; ++i )
  {
    if ( *(&a2->Data1 + i) != *(&IID_IeAxiAdminInstaller.Data1 + i) )
    {
      for ( j = 0; j != 4; ++j )
      {
        if ( *(&a2->Data1 + j) != *(&IID_IeAxiSystemInstaller.Data1 + j) )
        {
          v3 = -2147467262;
          goto LABEL_35;
        }
      }
      if ( !VerifyCallerIsSystemOrAdminWithHighIL()
        && (g_fRunningAsSystem || g_fRunningAsAdminWithHighIL)
        && (!*((_DWORD *)this + 5) || *((_DWORD *)this + 6)) )
      {
        v7 = (char *)this + 4;
        goto LABEL_13;
      }
      goto LABEL_24;
    }
  }
  if ( g_fRunningAsSystem )
  {
    if ( *((_DWORD *)this + 5) )
      goto LABEL_22;
  }
  else
  {
    if ( !*((_DWORD *)this + 5) )
    {
LABEL_23:
      *a3 = this;
      goto LABEL_14;
    }
LABEL_22:
    if ( !*((_DWORD *)this + 6) )
      goto LABEL_23;
  }
LABEL_24:
  v3 = -2147467259;
LABEL_35:
  *a3 = 0;
  return v3;
}

```

## disassembly

```asm
0x405a60  mov     edi, edi
0x405a62  push    ebp
0x405a63  mov     ebp, esp
0x405a65  mov     edx, [ebp+arg_4]
0x405a68  push    ebx
0x405a69  push    esi
0x405a6a  mov     esi, [ebp+this]
0x405a6d  xor     ebx, ebx
0x405a6f  push    edi
0x405a70  mov     edi, ebx
0x405a72  mov     ecx, ebx
0x405a74  mov     eax, [edx+ecx*4]
0x405a77  mov     ebx, offset _IID_IUnknown
0x405a7c  push    0
0x405a7e  cmp     eax, [ebx+ecx*4]
0x405a81  pop     ebx
0x405a82  jnz     short loc_405A8C
0x405a84  inc     ecx
0x405a85  cmp     ecx, 4
0x405a88  jnz     short loc_405A74
0x405a8a  jmp     short loc_405ABE
0x405a8c  mov     ecx, ebx
0x405a8e  mov     eax, [edx+ecx*4]
0x405a91  mov     ebx, offset _IID_IeAxiInstaller
0x405a96  push    0
0x405a98  cmp     eax, [ebx+ecx*4]
0x405a9b  pop     ebx
0x405a9c  jnz     short loc_405AA6
0x405a9e  inc     ecx
0x405a9f  cmp     ecx, 4
0x405aa2  jnz     short loc_405A8E
0x405aa4  jmp     short loc_405ABE
0x405aa6  mov     ecx, ebx
0x405aa8  mov     eax, [edx+ecx*4]
0x405aab  mov     ebx, offset _IID_IeAxiInstaller2
0x405ab0  push    0
0x405ab2  cmp     eax, [ebx+ecx*4]
0x405ab5  pop     ebx
0x405ab6  jnz     short loc_405AE3
0x405ab8  inc     ecx
0x405ab9  cmp     ecx, 4
0x405abc  jnz     short loc_405AA8
0x405abe  lea     eax, [esi+8]
0x405ac1  mov     ecx, esi
0x405ac3  neg     ecx
0x405ac5  sbb     ecx, ecx
0x405ac7  and     ecx, eax
0x405ac9  mov     eax, [ebp+arg_8]
0x405acc  mov     [eax], ecx
0x405ace  mov     eax, [esi]
0x405ad0  push    esi
0x405ad1  mov     esi, [eax+4]
0x405ad4  mov     ecx, esi
0x405ad6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x405adc  call    esi
0x405ade  jmp     loc_405B6F
0x405ae3  mov     ecx, ebx
0x405ae5  mov     eax, [edx+ecx*4]
0x405ae8  mov     ebx, offset _IID_IeAxiAdminInstaller
0x405aed  push    0
0x405aef  cmp     eax, [ebx+ecx*4]
0x405af2  pop     ebx
0x405af3  jnz     short loc_405B22
0x405af5  inc     ecx
0x405af6  cmp     ecx, 4
0x405af9  jnz     short loc_405AE5
0x405afb  cmp     ?g_fRunningAsSystem@@3HA, edi; int g_fRunningAsSystem
0x405b01  jnz     short loc_405B0A
0x405b03  cmp     [esi+14h], ebx
0x405b06  jz      short loc_405B14
0x405b08  jmp     short loc_405B0F
0x405b0a  cmp     [esi+14h], ebx
0x405b0d  jz      short loc_405B1B
0x405b0f  cmp     [esi+18h], ebx
0x405b12  jnz     short loc_405B1B
0x405b14  mov     eax, [ebp+arg_8]
0x405b17  mov     [eax], esi
0x405b19  jmp     short loc_405ACE
0x405b1b  mov     edi, 80004005h
0x405b20  jmp     short loc_405B6A
0x405b22  mov     ecx, ebx
0x405b24  mov     eax, [edx+ecx*4]
0x405b27  mov     ebx, offset _IID_IeAxiSystemInstaller
0x405b2c  push    0
0x405b2e  cmp     eax, [ebx+ecx*4]
0x405b31  pop     ebx
0x405b32  jnz     short loc_405B65
0x405b34  inc     ecx
0x405b35  cmp     ecx, 4
0x405b38  jnz     short loc_405B24
0x405b3a  call    ?VerifyCallerIsSystemOrAdminWithHighIL@@YGJXZ; VerifyCallerIsSystemOrAdminWithHighIL(void)
0x405b3f  test    eax, eax
0x405b41  jnz     short loc_405B1B
0x405b43  cmp     ?g_fRunningAsSystem@@3HA, edi; int g_fRunningAsSystem
0x405b49  jnz     short loc_405B53
0x405b4b  cmp     ?g_fRunningAsAdminWithHighIL@@3HA, edi; int g_fRunningAsAdminWithHighIL
0x405b51  jz      short loc_405B1B
0x405b53  cmp     [esi+14h], ebx
0x405b56  jz      short loc_405B5D
0x405b58  cmp     [esi+18h], ebx
0x405b5b  jz      short loc_405B1B
0x405b5d  lea     eax, [esi+4]
0x405b60  jmp     loc_405AC1
0x405b65  mov     edi, 80004002h
0x405b6a  mov     eax, [ebp+arg_8]
0x405b6d  mov     [eax], ebx
0x405b6f  mov     eax, edi
0x405b71  pop     edi
0x405b72  pop     esi
0x405b73  pop     ebx
0x405b74  pop     ebp
0x405b75  retn    0Ch
```
