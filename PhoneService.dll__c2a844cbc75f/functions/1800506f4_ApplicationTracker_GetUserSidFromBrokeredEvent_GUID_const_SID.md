# ApplicationTracker::GetUserSidFromBrokeredEvent(_GUID const *,_SID * *)

- ea: `0x1800506f4`
- end: `0x1800507d6`
- name: `?GetUserSidFromBrokeredEvent@ApplicationTracker@@KAJPEBU_GUID@@PEAPEAU_SID@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _SID **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001787c`
- `0x1800507dc`

## callees

- `0x180006e94`
- `0x1800506f4`
- `0x180050fd8`
- `0x18008d9b0`

## import_xrefs

- `PhoneUtil!DuplicateSidIfValid` at `0x18005078c`
- `PhoneUtil!DuplicateSidIfValid` at `0x18005078c`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18005075a`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x1800507b6`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18005075a`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x1800507b6`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryBrokeredEvent` at `0x18005072a`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryBrokeredEvent` at `0x18005072a`

## pseudocode

```c
__int64 __fastcall ApplicationTracker::GetUserSidFromBrokeredEvent(const struct _GUID *a1, struct _SID **a2)
{
  int v3; // eax
  BackTraceCollection *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+38h] [rbp-20h] BYREF

  v13 = 0;
  v12 = 0;
  v3 = BiQueryBrokeredEvent(a1, &v13, &v12);
  if ( v3 < 0 )
  {
    v5 = v3 | 0x10000000;
    BackTraceCollection::Capture(v4, v3 | 0x10000000);
    v7 = 332;
LABEL_3:
    v8 = 0;
LABEL_4:
    Log_HREvent_10(v5, v8, v6, v7);
    if ( v12 )
      BiFreeMemory();
    return v5;
  }
  if ( !*(_DWORD *)(v12 + 40) )
  {
    v5 = -2147418113;
    BackTraceCollection::Capture(v4, -2147418113);
    v7 = 334;
    goto LABEL_3;
  }
  v10 = DuplicateSidIfValid((void *)(v12 + *(unsigned int *)(v12 + 40)), a2);
  v5 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    v8 = 1;
    v7 = 336;
    goto LABEL_4;
  }
  if ( v12 )
    BiFreeMemory();
  return 0;
}

```

## disassembly

```asm
0x1800506f4  mov     r11, rsp
0x1800506f7  mov     [r11+18h], rbx
0x1800506fb  push    rdi
0x1800506fc  sub     rsp, 50h
0x180050700  mov     rax, cs:__security_cookie
0x180050707  xor     rax, rsp
0x18005070a  mov     [rsp+58h+var_18], rax
0x18005070f  mov     rdi, rdx
0x180050712  mov     [rsp+58h+var_20], 0
0x18005071a  lea     rdx, [r11-20h]
0x18005071e  mov     qword ptr [r11-28h], 0
0x180050726  lea     r8, [r11-28h]
0x18005072a  call    cs:__imp_BiQueryBrokeredEvent
0x180050730  mov     ebx, eax
0x180050732  test    eax, eax
0x180050734  jns     short loc_180050764
0x180050736  bts     ebx, 1Ch
0x18005073a  mov     edx, ebx; int
0x18005073c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050741  mov     r9d, 14Ch
0x180050747  xor     edx, edx
0x180050749  mov     ecx, ebx
0x18005074b  call    Log_HREvent_10
0x180050750  mov     rcx, [rsp+58h+var_28]
0x180050755  test    rcx, rcx
0x180050758  jz      short loc_180050760
0x18005075a  call    cs:__imp_BiFreeMemory
0x180050760  mov     eax, ebx
0x180050762  jmp     short loc_1800507BE
0x180050764  mov     rax, [rsp+58h+var_28]
0x180050769  cmp     dword ptr [rax+28h], 0
0x18005076d  jnz     short loc_180050783
0x18005076f  mov     ebx, 8000FFFFh
0x180050774  mov     edx, ebx; int
0x180050776  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005077b  mov     r9d, 14Eh
0x180050781  jmp     short loc_180050747
0x180050783  mov     ecx, [rax+28h]
0x180050786  mov     rdx, rdi
0x180050789  add     rcx, rax
0x18005078c  call    cs:__imp_?DuplicateSidIfValid@@YAJPEAXPEAPEAU_SID@@@Z; DuplicateSidIfValid(void *,_SID * *)
0x180050792  mov     ebx, eax
0x180050794  test    eax, eax
0x180050796  jns     short loc_1800507AC
0x180050798  mov     edx, eax; int
0x18005079a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005079f  mov     edx, 1
0x1800507a4  mov     r9d, 150h
0x1800507aa  jmp     short loc_180050749
0x1800507ac  mov     rcx, [rsp+58h+var_28]
0x1800507b1  test    rcx, rcx
0x1800507b4  jz      short loc_1800507BC
0x1800507b6  call    cs:__imp_BiFreeMemory
0x1800507bc  xor     eax, eax
0x1800507be  mov     rcx, [rsp+58h+var_18]
0x1800507c3  xor     rcx, rsp; StackCookie
0x1800507c6  call    __security_check_cookie
0x1800507cb  mov     rbx, [rsp+58h+arg_10]
0x1800507d0  add     rsp, 50h
0x1800507d4  pop     rdi
0x1800507d5  retn
```
