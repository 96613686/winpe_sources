# MakeUniqueTempDirectory(char const *,char *,ulong)

- ea: `0x407a3f`
- end: `0x407b99`
- name: `?MakeUniqueTempDirectory@@YGJPBDPADK@Z`
- size: `346`
- prototype: `int __userpurge@<eax>(char *@<edx>, const CHAR *@<ecx>, const char *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x407ca8`

## callees

- `0x4064be`
- `0x40767c`
- `0x40784b`
- `0x407a3f`
- `0x40cb60`

## import_xrefs

- `KERNEL32!CreateDirectoryExA` at `0x407b1d`
- `KERNEL32!CreateDirectoryExA` at `0x407b1d`
- `KERNEL32!GetFileAttributesA` at `0x407aaf`
- `KERNEL32!GetFileAttributesA` at `0x407aaf`
- `KERNEL32!LocalFree` at `0x407b57`
- `KERNEL32!LocalFree` at `0x407b6c`
- `KERNEL32!LocalFree` at `0x407b57`
- `KERNEL32!LocalFree` at `0x407b6c`
- `KERNEL32!LeaveCriticalSection` at `0x407b80`
- `KERNEL32!LeaveCriticalSection` at `0x407b80`
- `KERNEL32!EnterCriticalSection` at `0x407a75`
- `KERNEL32!EnterCriticalSection` at `0x407a75`
- `KERNEL32!GetLastError` at `0x407b27`
- `KERNEL32!GetLastError` at `0x407b27`

## pseudocode

```c
int __userpurge MakeUniqueTempDirectory@<eax>(
        char *a1@<edx>,
        const CHAR *a2@<ecx>,
        const char *a3,
        char *a4,
        unsigned int a5)
{
  int v5; // ebx
  signed int Directory; // esi
  signed int LastError; // eax
  int v10; // [esp-4h] [ebp-158h]
  struct _ACL **v11; // [esp+0h] [ebp-154h]
  void **v12; // [esp+4h] [ebp-150h]
  _SECURITY_ATTRIBUTES SecurityAttributes; // [esp+Ch] [ebp-148h] BYREF
  HLOCAL v14; // [esp+18h] [ebp-13Ch] BYREF
  HLOCAL hMem; // [esp+1Ch] [ebp-138h] BYREF
  LPCSTR lpTemplateDirectory; // [esp+20h] [ebp-134h]
  struct _EXPLICIT_ACCESS_W v17[3]; // [esp+24h] [ebp-130h] BYREF
  struct _SECURITY_ATTRIBUTES v18; // [esp+84h] [ebp-D0h] BYREF
  _EXPLICIT_ACCESS_W v19; // [esp+C8h] [ebp-8Ch] BYREF
  WCHAR v20[34]; // [esp+10Ch] [ebp-48h] BYREF

  lpTemplateDirectory = a2;
  v5 = 1;
  Directory = -2147467259;
  if ( !g_oLock )
    goto LABEL_4;
  EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    a2 = lpTemplateDirectory;
LABEL_4:
    if ( v5 > 500 )
      break;
    v10 = v5++;
    Directory = StringCchPrintfA(a1, 0x104u, "%s%s%d.tmp", a2, "IDC", v10);
    if ( Directory < 0 )
      goto LABEL_19;
    if ( GetFileAttributesA(a1) == -1 )
      goto LABEL_9;
  }
  if ( Directory < 0 )
    goto LABEL_19;
LABEL_9:
  hMem = 0;
  v14 = 0;
  Directory = SetSecurityAttributes(v17, &SecurityAttributes, &v18, &v19, v20, (PACL *)&hMem, &v14, v11, v12);
  if ( Directory >= 0 )
  {
    if ( CreateDirectoryExA(lpTemplateDirectory, a1, &SecurityAttributes) )
      goto LABEL_14;
    LastError = GetLastError();
    Directory = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      Directory = LastError;
    if ( Directory >= 0 )
LABEL_14:
      Directory = EnsureACILCanReadDirectory(a1);
    if ( hMem )
      LocalFree(hMem);
    if ( v14 )
      LocalFree(v14);
  }
LABEL_19:
  if ( g_oLock )
    LeaveCriticalSection(&CriticalSection);
  return Directory;
}

```

## disassembly

```asm
0x407a3f  mov     edi, edi
0x407a41  push    ebp
0x407a42  mov     ebp, esp
0x407a44  sub     esp, 148h
0x407a4a  mov     eax, ___security_cookie
0x407a4f  xor     eax, ebp
0x407a51  mov     [ebp+var_4], eax
0x407a54  push    ebx
0x407a55  xor     ebx, ebx
0x407a57  mov     [ebp+lpTemplateDirectory], ecx
0x407a5d  push    esi; void **
0x407a5e  inc     ebx
0x407a5f  mov     esi, 80004005h
0x407a64  cmp     ?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x407a6b  push    edi; char *
0x407a6c  mov     edi, edx
0x407a6e  jz      short loc_407A81
0x407a70  push    offset CriticalSection; lpCriticalSection
0x407a75  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x407a7b  mov     ecx, [ebp+lpTemplateDirectory]
0x407a81  cmp     ebx, 1F4h
0x407a87  jg      short loc_407ABC
0x407a89  push    ebx
0x407a8a  push    offset aIdc_0; "IDC"
0x407a8f  push    ecx
0x407a90  push    offset aSSDTmp; "%s%s%d.tmp"
0x407a95  push    104h; unsigned int
0x407a9a  push    edi; Buffer
0x407a9b  inc     ebx
0x407a9c  call    ?StringCchPrintfA@@YAJPADIPBDZZ; StringCchPrintfA(char *,uint,char const *,...)
0x407aa1  mov     esi, eax
0x407aa3  add     esp, 18h
0x407aa6  test    esi, esi
0x407aa8  js      loc_407B72
0x407aae  push    edi; lpFileName
0x407aaf  call    ds:__imp__GetFileAttributesA@4; GetFileAttributesA(x)
0x407ab5  cmp     eax, 0FFFFFFFFh
0x407ab8  jz      short loc_407AC4
0x407aba  jmp     short loc_407A7B
0x407abc  test    esi, esi
0x407abe  js      loc_407B72
0x407ac4  lea     eax, [ebp+var_13C]
0x407aca  mov     [ebp+hMem], 0
0x407ad4  push    eax; void *
0x407ad5  lea     eax, [ebp+hMem]
0x407adb  mov     [ebp+var_13C], 0
0x407ae5  push    eax; void *
0x407ae6  lea     eax, [ebp+var_48]
0x407ae9  push    eax; void *
0x407aea  lea     eax, [ebp+var_8C]
0x407af0  push    eax; struct _EXPLICIT_ACCESS_W *
0x407af1  lea     eax, [ebp+var_D0]
0x407af7  push    eax; struct _SECURITY_ATTRIBUTES *
0x407af8  lea     edx, [ebp+var_130]
0x407afe  lea     ecx, [ebp+SecurityAttributes]
0x407b04  call    ?SetSecurityAttributes@@YGJPAU_SECURITY_ATTRIBUTES@@QAU_EXPLICIT_ACCESS_W@@PAX22PAPAU_ACL@@PAPAX@Z; SetSecurityAttributes(_SECURITY_ATTRIBUTES *,_EXPLICIT_ACCESS_W * const,void *,void *,void *,_ACL * *,void * *)
0x407b09  mov     esi, eax
0x407b0b  test    esi, esi
0x407b0d  js      short loc_407B72
0x407b0f  lea     eax, [ebp+SecurityAttributes]
0x407b15  push    eax; lpSecurityAttributes
0x407b16  push    edi; lpNewDirectory
0x407b17  push    [ebp+lpTemplateDirectory]; lpTemplateDirectory
0x407b1d  call    ds:__imp__CreateDirectoryExA@12; CreateDirectoryExA(x,x,x)
0x407b23  test    eax, eax
0x407b25  jnz     short loc_407B3F
0x407b27  call    ds:__imp__GetLastError@0; GetLastError()
0x407b2d  movzx   esi, ax
0x407b30  or      esi, 80070000h
0x407b36  test    eax, eax
0x407b38  cmovle  esi, eax
0x407b3b  test    esi, esi
0x407b3d  js      short loc_407B48
0x407b3f  mov     ecx, edi
0x407b41  call    ?EnsureACILCanReadDirectory@@YGJPBD@Z; EnsureACILCanReadDirectory(char const *)
0x407b46  mov     esi, eax
0x407b48  cmp     [ebp+hMem], 0
0x407b4f  jz      short loc_407B5D
0x407b51  push    [ebp+hMem]; hMem
0x407b57  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407b5d  cmp     [ebp+var_13C], 0
0x407b64  jz      short loc_407B72
0x407b66  push    [ebp+var_13C]; hMem
0x407b6c  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407b72  cmp     ?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x407b79  jz      short loc_407B86
0x407b7b  push    offset CriticalSection; lpCriticalSection
0x407b80  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x407b86  mov     ecx, [ebp+var_4]
0x407b89  mov     eax, esi
0x407b8b  pop     edi
0x407b8c  pop     esi
0x407b8d  xor     ecx, ebp; StackCookie
0x407b8f  pop     ebx
0x407b90  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407b95  leave
0x407b96  retn    4
```
