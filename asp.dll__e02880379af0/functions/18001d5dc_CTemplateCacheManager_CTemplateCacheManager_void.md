# CTemplateCacheManager::~CTemplateCacheManager(void)

- ea: `0x18001d5dc`
- end: `0x18001d642`
- name: `??1CTemplateCacheManager@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CTemplateCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800244e0`

## callees

- `0x18001d5dc`

## import_xrefs

- `KERNEL32!RemoveDirectoryA` at `0x18001d623`
- `KERNEL32!RemoveDirectoryA` at `0x18001d623`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001d60d`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001d636`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001d60d`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001d636`
- `KERNEL32!GetCurrentProcess` at `0x18001d5ea`
- `KERNEL32!GetCurrentProcess` at `0x18001d5ea`
- `KERNEL32!IsWow64Process` at `0x18001d5f8`
- `KERNEL32!IsWow64Process` at `0x18001d5f8`

## pseudocode

```c
void __fastcall CTemplateCacheManager::~CTemplateCacheManager(CTemplateCacheManager *this)
{
  HANDLE CurrentProcess; // rax
  BOOL v2; // ebx
  BOOL Wow64Process; // [rsp+38h] [rbp+10h] BYREF

  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  v2 = IsWow64Process(CurrentProcess, &Wow64Process);
  if ( v2 && Wow64Process )
    Wow64EnableWow64FsRedirection(0);
  if ( !CTemplateCacheManager::m_fFailedToInitPersistCache )
    RemoveDirectoryA(&CTemplateCacheManager::m_szPersistCacheDir);
  if ( v2 )
  {
    if ( Wow64Process )
      Wow64EnableWow64FsRedirection(1u);
  }
}

```

## disassembly

```asm
0x18001d5dc  push    rbx
0x18001d5de  sub     rsp, 20h
0x18001d5e2  mov     [rsp+28h+Wow64Process], 0
0x18001d5ea  call    cs:__imp_GetCurrentProcess
0x18001d5f0  mov     rcx, rax; hProcess
0x18001d5f3  lea     rdx, [rsp+28h+Wow64Process]; Wow64Process
0x18001d5f8  call    cs:__imp_IsWow64Process
0x18001d5fe  mov     ebx, eax
0x18001d600  test    eax, eax
0x18001d602  jz      short loc_18001D613
0x18001d604  cmp     [rsp+28h+Wow64Process], 0
0x18001d609  jz      short loc_18001D613
0x18001d60b  xor     ecx, ecx; Wow64FsEnableRedirection
0x18001d60d  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18001d613  cmp     cs:?m_fFailedToInitPersistCache@CTemplateCacheManager@@0HA, 0; int CTemplateCacheManager::m_fFailedToInitPersistCache
0x18001d61a  jnz     short loc_18001D629
0x18001d61c  lea     rcx, ?m_szPersistCacheDir@CTemplateCacheManager@@0PADA; lpPathName
0x18001d623  call    cs:__imp_RemoveDirectoryA
0x18001d629  test    ebx, ebx
0x18001d62b  jz      short loc_18001D63C
0x18001d62d  cmp     [rsp+28h+Wow64Process], 0
0x18001d632  jz      short loc_18001D63C
0x18001d634  mov     cl, 1; Wow64FsEnableRedirection
0x18001d636  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18001d63c  add     rsp, 20h
0x18001d640  pop     rbx
0x18001d641  retn
```
