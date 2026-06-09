# CActiveXInstallSecurityManager::QueryInterface(_GUID const &,void * *)

- ea: `0x408ce0`
- end: `0x408d44`
- name: `?QueryInterface@CActiveXInstallSecurityManager@@UAGJABU_GUID@@PAPAX@Z`
- size: `100`
- prototype: `int __stdcall(CActiveXInstallSecurityManager *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x408ce0`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CActiveXInstallSecurityManager::QueryInterface(
        CActiveXInstallSecurityManager *this,
        const struct _GUID *a2,
        void **a3)
{
  int v3; // edi
  int v4; // ecx
  int v5; // ecx

  v3 = 0;
  v4 = 0;
  while ( *(&a2->Data1 + v4) == *(&IID_IUnknown.Data1 + v4) )
  {
    if ( ++v4 == 4 )
    {
LABEL_8:
      *a3 = this;
      (*(void (__thiscall **)(_DWORD, CActiveXInstallSecurityManager *))(*(_DWORD *)this + 4))(
        *(_DWORD *)(*(_DWORD *)this + 4),
        this);
      return v3;
    }
  }
  v5 = 0;
  while ( *(&a2->Data1 + v5) == *(&IID_IInternetHostSecurityManager.Data1 + v5) )
  {
    if ( ++v5 == 4 )
      goto LABEL_8;
  }
  *a3 = 0;
  return -2147467262;
}

```

## disassembly

```asm
0x408ce0  mov     edi, edi
0x408ce2  push    ebp
0x408ce3  mov     ebp, esp
0x408ce5  mov     edx, [ebp+arg_4]
0x408ce8  push    esi
0x408ce9  push    edi
0x408cea  xor     edi, edi
0x408cec  mov     esi, offset _IID_IUnknown
0x408cf1  xor     ecx, ecx
0x408cf3  mov     eax, [edx+ecx*4]
0x408cf6  cmp     eax, [esi+ecx*4]
0x408cf9  jnz     short loc_408D03
0x408cfb  inc     ecx
0x408cfc  cmp     ecx, 4
0x408cff  jnz     short loc_408CF3
0x408d01  jmp     short loc_408D18
0x408d03  mov     esi, offset _IID_IInternetHostSecurityManager
0x408d08  xor     ecx, ecx
0x408d0a  mov     eax, [edx+ecx*4]
0x408d0d  cmp     eax, [esi+ecx*4]
0x408d10  jnz     short loc_408D32
0x408d12  inc     ecx
0x408d13  cmp     ecx, 4
0x408d16  jnz     short loc_408D0A
0x408d18  mov     ecx, [ebp+this]
0x408d1b  mov     eax, [ebp+arg_8]
0x408d1e  push    ecx
0x408d1f  mov     [eax], ecx
0x408d21  mov     eax, [ecx]
0x408d23  mov     esi, [eax+4]
0x408d26  mov     ecx, esi
0x408d28  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x408d2e  call    esi
0x408d30  jmp     short loc_408D3C
0x408d32  mov     eax, [ebp+arg_8]
0x408d35  mov     [eax], edi
0x408d37  mov     edi, 80004002h
0x408d3c  mov     eax, edi
0x408d3e  pop     edi
0x408d3f  pop     esi
0x408d40  pop     ebp
0x408d41  retn    0Ch
```
