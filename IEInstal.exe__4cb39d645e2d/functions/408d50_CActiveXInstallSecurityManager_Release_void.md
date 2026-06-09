# CActiveXInstallSecurityManager::Release(void)

- ea: `0x408d50`
- end: `0x408d85`
- name: `?Release@CActiveXInstallSecurityManager@@UAGKXZ`
- size: `53`
- prototype: `int __stdcall(CActiveXInstallSecurityManager *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x402712`
- `0x408c35`
- `0x408d50`

## pseudocode

```c
int __stdcall CActiveXInstallSecurityManager::Release(CActiveXInstallSecurityManager *this)
{
  int v1; // edi

  v1 = *((_DWORD *)this + 1) - 1;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) )
  {
    v1 = 0;
    if ( this )
    {
      CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(this);
      operator delete(this);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x408d50  mov     edi, edi
0x408d52  push    ebp
0x408d53  mov     ebp, esp
0x408d55  push    esi
0x408d56  mov     esi, [ebp+lpMem]
0x408d59  or      eax, 0FFFFFFFFh
0x408d5c  push    edi
0x408d5d  lea     ecx, [esi+4]
0x408d60  mov     edi, [ecx]
0x408d62  dec     edi
0x408d63  lock xadd [ecx], eax
0x408d67  jnz     short loc_408D7D
0x408d69  xor     edi, edi
0x408d6b  test    esi, esi
0x408d6d  jz      short loc_408D7D
0x408d6f  mov     ecx, esi; this
0x408d71  call    ??1CActiveXInstallSecurityManager@@QAE@XZ; CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(void)
0x408d76  push    esi; lpMem
0x408d77  call    ??3@YAXPAX@Z; operator delete(void *)
0x408d7c  pop     ecx
0x408d7d  mov     eax, edi
0x408d7f  pop     edi
0x408d80  pop     esi
0x408d81  pop     ebp
0x408d82  retn    4
```
