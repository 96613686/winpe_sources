# HandlerProc

- ea: `0x180030780`
- end: `0x1800308a8`
- name: `HandlerProc`
- size: `296`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180030780`
- `0x1800308b0`
- `0x1800458e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003089d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003089d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180030890`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180030890`

## pseudocode

```c
__int64 __fastcall HandlerProc(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx
  int v9; // ecx

  v4 = 0;
  v5 = dwControl - 1;
  if ( !v5 )
  {
LABEL_14:
    _m_prefetchw(&dword_180110068);
    if ( (_InterlockedOr(&dword_180110068, 3u) & 1) == 0 )
    {
      *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwCheckPoint = 0;
      ServiceStatus.dwWaitHint = 30000;
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      SetEvent(hObject);
    }
    goto LABEL_6;
  }
  v6 = v5 - 10;
  if ( v6 )
  {
    v7 = v6 - 2;
    if ( !v7 )
    {
      _m_prefetchw(&dword_180110068);
      if ( (_InterlockedOr(&dword_180110068, 2u) & 1) == 0 )
        sub_1800308B0(dwEventType, (__int64)lpEventData, (__int64)lpEventData, dwEventType);
      goto LABEL_6;
    }
    v9 = v7 - 2;
    if ( v9 )
    {
      if ( v9 == 17 )
      {
        _m_prefetchw(&dword_180110068);
        if ( (_InterlockedOr(&dword_180110068, 2u) & 1) != 0 )
          v4 = 1115;
      }
      else
      {
        v4 = 120;
      }
      goto LABEL_6;
    }
    goto LABEL_14;
  }
  _m_prefetchw(&dword_180110068);
  if ( (_InterlockedOr(&dword_180110068, 2u) & 1) == 0 )
    sub_1800458E4(dwEventType, lpEventData);
LABEL_6:
  _InterlockedAnd(&dword_180110068, 0xFFFFFFFD);
  return v4;
}

```

## disassembly

```asm
0x180030780  push    rbx
0x180030782  sub     rsp, 20h
0x180030786  xor     ebx, ebx
0x180030788  mov     r9d, edx
0x18003078b  sub     ecx, 1
0x18003078e  jz      loc_180030843
0x180030794  sub     ecx, 0Ah
0x180030797  jz      short loc_180030813
0x180030799  sub     ecx, 2
0x18003079c  jnz     short loc_1800307DB
0x18003079e  prefetchw byte ptr cs:dword_180110068
0x1800307a5  mov     eax, cs:dword_180110068
0x1800307ab  mov     ecx, eax
0x1800307ad  or      ecx, 2
0x1800307b0  lock cmpxchg cs:dword_180110068, ecx
0x1800307b8  jnz     short loc_1800307AB
0x1800307ba  test    al, 1
0x1800307bc  jz      short loc_1800307CE
0x1800307be  lock and cs:dword_180110068, 0FFFFFFFDh
0x1800307c6  mov     eax, ebx
0x1800307c8  add     rsp, 20h
0x1800307cc  pop     rbx
0x1800307cd  retn
0x1800307ce  mov     rdx, r8
0x1800307d1  mov     ecx, r9d
0x1800307d4  call    sub_1800308B0
0x1800307d9  jmp     short loc_1800307BE
0x1800307db  sub     ecx, 2
0x1800307de  jz      short loc_180030843
0x1800307e0  cmp     ecx, 11h
0x1800307e3  jz      short loc_1800307EC
0x1800307e5  mov     ebx, 78h ; 'x'
0x1800307ea  jmp     short loc_1800307BE
0x1800307ec  prefetchw byte ptr cs:dword_180110068
0x1800307f3  mov     eax, cs:dword_180110068
0x1800307f9  mov     ecx, eax
0x1800307fb  or      ecx, 2
0x1800307fe  lock cmpxchg cs:dword_180110068, ecx
0x180030806  jnz     short loc_1800307F9
0x180030808  test    al, 1
0x18003080a  jz      short loc_1800307BE
0x18003080c  mov     ebx, 45Bh
0x180030811  jmp     short loc_1800307BE
0x180030813  prefetchw byte ptr cs:dword_180110068
0x18003081a  mov     eax, cs:dword_180110068
0x180030820  mov     ecx, eax
0x180030822  or      ecx, 2
0x180030825  lock cmpxchg cs:dword_180110068, ecx
0x18003082d  jnz     short loc_180030820
0x18003082f  test    al, 1
0x180030831  jnz     short loc_1800307BE
0x180030833  mov     rdx, r8
0x180030836  mov     ecx, r9d
0x180030839  call    sub_1800458E4
0x18003083e  jmp     loc_1800307BE
0x180030843  prefetchw byte ptr cs:dword_180110068
0x18003084a  mov     eax, cs:dword_180110068
0x180030850  mov     ecx, eax
0x180030852  or      ecx, 3
0x180030855  lock cmpxchg cs:dword_180110068, ecx
0x18003085d  jnz     short loc_180030850
0x18003085f  test    al, 1
0x180030861  jnz     loc_1800307BE
0x180030867  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x18003086e  lea     rdx, ServiceStatus; lpServiceStatus
0x180030875  mov     qword ptr cs:ServiceStatus.dwCurrentState, 3
0x180030880  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x180030886  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x180030890  call    cs:SetServiceStatus
0x180030896  mov     rcx, cs:hObject; hEvent
0x18003089d  call    cs:SetEvent
0x1800308a3  jmp     loc_1800307BE
```
