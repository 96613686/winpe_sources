# DeleteScheduledTaskToRemoveRetailDemoFoldersTask::Execute(void)

- ea: `0x180026030`
- end: `0x1800260a4`
- name: `?Execute@DeleteScheduledTaskToRemoveRetailDemoFoldersTask@@MEAAXXZ`
- size: `116`
- prototype: `void __fastcall(DeleteScheduledTaskToRemoveRetailDemoFoldersTask *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001094c`
- `0x180025f1c`
- `0x180026030`
- `0x18002e174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026042`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026042`

## string_xrefs

- `0x180026034`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\RetailDemo Offline Content`
- `0x180026082`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\deletescheduledtasktoremoveretaildemofolders.cpp`

## pseudocode

```c
void __fastcall DeleteScheduledTaskToRemoveRetailDemoFoldersTask::Execute(
        DeleteScheduledTaskToRemoveRetailDemoFoldersTask *this)
{
  LSTATUS v1; // eax
  unsigned __int64 v2; // r9
  bool v3; // sf
  bool v4; // al
  __int64 v5; // rcx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = RegDeleteTreeW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\RetailDemo Offline Content");
  v2 = (unsigned int)v1;
  v3 = v1 < 0;
  if ( v1 > 0 )
    v3 = 1;
  v4 = v3 && (unsigned int)(v1 - 2) > 1;
  if ( (int)v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\deletescheduledtasktoremoveretaildemofolders.cpp",
      (const char *)v2,
      v6);
  RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders((RetailDemoUtil *)0x80070000LL);
  LOBYTE(v5) = 1;
  RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<3,bool>(v5);
}

```

## disassembly

```asm
0x180026030  sub     rsp, 28h
0x180026034  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002603b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026042  call    cs:__imp_RegDeleteTreeW
0x180026048  mov     r9d, eax
0x18002604b  mov     ecx, 80070000h; this
0x180026050  test    eax, eax
0x180026052  jle     short loc_18002605C
0x180026054  movzx   eax, r9w
0x180026058  or      eax, ecx
0x18002605a  test    eax, eax
0x18002605c  jns     short loc_18002606B
0x18002605e  lea     eax, [r9-2]
0x180026062  cmp     eax, 1
0x180026065  jbe     short loc_18002606B
0x180026067  mov     al, 1
0x180026069  jmp     short loc_18002606D
0x18002606b  xor     al, al
0x18002606d  test    r9d, r9d
0x180026070  jle     short loc_180026079
0x180026072  movzx   r9d, r9w
0x180026076  or      r9d, ecx; char *
0x180026079  test    al, al
0x18002607b  jz      short loc_180026094
0x18002607d  mov     rcx, [rsp+28h]; this
0x180026082  lea     r8, aPcshellShellRe_34; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026089  mov     edx, 14h; void *
0x18002608e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026094  call    ?DeleteScheduledTaskToRemoveRetailDemoFolders@RetailDemoUtil@@YAXXZ; RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders(void)
0x180026099  mov     cl, 1
0x18002609b  add     rsp, 28h
0x18002609f  jmp     ??$HandleEvent@$02_N@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAX_N@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<3,bool>(bool)
```
