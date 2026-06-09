# HandleAddDrivesRequest(TASK_ADD_DRIVES_REQUEST const *,uint *)

- ea: `0x14001913c`
- end: `0x14001930a`
- name: `?HandleAddDrivesRequest@@YAHPEBUTASK_ADD_DRIVES_REQUEST@@PEAI@Z`
- size: `462`
- prototype: `__int64 __fastcall(const struct TASK_ADD_DRIVES_REQUEST *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x140017d70`

## callees

- `0x14000a440`
- `0x14000b354`
- `0x1400148c4`
- `0x140015604`
- `0x14001593c`
- `0x140016900`
- `0x14001832c`
- `0x14001913c`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400192c2`
- `KERNEL32!LocalFree` at `0x1400192d3`
- `KERNEL32!LocalFree` at `0x1400192e1`
- `KERNEL32!LocalFree` at `0x1400192c2`
- `KERNEL32!LocalFree` at `0x1400192d3`
- `KERNEL32!LocalFree` at `0x1400192e1`
- `KERNEL32!SleepEx` at `0x1400192b1`
- `KERNEL32!SleepEx` at `0x1400192b1`
- `KERNEL32!SetLastError` at `0x1400191ae`
- `KERNEL32!SetLastError` at `0x14001922b`
- `KERNEL32!SetLastError` at `0x1400191ae`
- `KERNEL32!SetLastError` at `0x14001922b`

## pseudocode

```c
__int64 __fastcall HandleAddDrivesRequest(const struct TASK_ADD_DRIVES_REQUEST *a1, unsigned int *a2)
{
  unsigned int v4; // ebx
  unsigned int Pool; // eax
  char *v6; // rsi
  unsigned int v7; // eax
  int v8; // r9d
  unsigned int v9; // eax
  int v10; // r9d
  HLOCAL v12; // [rsp+20h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-28h] BYREF
  HLOCAL v14; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID InBuffer; // [rsp+38h] [rbp-18h] BYREF

  hMem = 0;
  v12 = 0;
  InBuffer = GUID_NULL;
  v14 = 0;
  *a2 = -1;
  v4 = IssueProgressStringResult(32883);
  if ( !v4 )
    return v4;
  if ( *(_QWORD *)a1 < 8u || *(_QWORD *)a1 != 4LL * *((unsigned int *)a1 + 9) + 40 )
  {
    v4 = 0;
    SetLastError(0x18u);
    return v4;
  }
  InBuffer = (struct _GUID)*((_OWORD *)a1 + 1);
  Pool = SiGetPool(&InBuffer, 0, (struct _SU_POOL_OBJECT **)&v14);
  v6 = (char *)v14;
  v4 = Pool;
  if ( Pool )
  {
    v4 = SuInitializeDriveTemplateList(
           *((_DWORD *)a1 + 9),
           (const unsigned int *)a1 + 10,
           (struct _SP_DRIVE_INFO **)&hMem,
           (unsigned int **)&v12);
    if ( v4 )
    {
      v7 = SuNumberOfErrors(*((_DWORD *)a1 + 9), (const unsigned int *)v12);
      if ( v8 != v7 )
      {
        v4 = IssueProgressStringResult(32897);
        if ( !v4 )
          goto LABEL_16;
        v4 = SuAddDrivesEx(
               (struct _SU_POOL_OBJECT *)v6,
               *((_DWORD *)a1 + 9),
               (struct _SP_DRIVE_INFO *)hMem,
               (unsigned int *)v12);
        if ( !v4 )
          goto LABEL_16;
        v9 = SuNumberOfErrors(*((_DWORD *)a1 + 9), (const unsigned int *)v12);
        if ( v10 != v9 )
        {
          *a2 = v9;
          SuAutoRepairSpaces((const struct _GUID *)(v6 + 40));
          if ( *((_DWORD *)a1 + 8) )
          {
            v4 = IssueProgressStringResult(32904);
            if ( v4 )
            {
              v4 = SuRebalancePool(&InBuffer);
              if ( v4 )
                SleepEx(0x3E8u, 0);
            }
          }
          goto LABEL_16;
        }
      }
      v4 = 0;
      SetLastError(0xFu);
    }
LABEL_16:
    if ( hMem )
      LocalFree(hMem);
    if ( v12 )
      LocalFree(v12);
  }
  if ( v6 )
    LocalFree(v6);
  return v4;
}

```

## disassembly

```asm
0x14001913c  mov     [rsp-18h+arg_10], rbx
0x140019141  mov     [rsp-18h+arg_18], rsi
0x140019146  push    rbp
0x140019147  push    rdi
0x140019148  push    r12
0x14001914a  mov     rbp, rsp
0x14001914d  sub     rsp, 50h
0x140019151  mov     rax, cs:__security_cookie
0x140019158  xor     rax, rsp
0x14001915b  mov     [rbp+var_8], rax
0x14001915f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140019166  mov     rdi, rcx
0x140019169  mov     [rbp+hMem], 0
0x140019171  mov     ecx, 8073h
0x140019176  mov     [rbp+var_30], 0
0x14001917e  movdqu  xmmword ptr [rbp+InBuffer.Data1], xmm0
0x140019183  mov     r12, rdx
0x140019186  mov     [rbp+var_20], 0
0x14001918e  mov     dword ptr [rdx], 0FFFFFFFFh
0x140019194  call    IssueProgressStringResult
0x140019199  mov     ebx, eax
0x14001919b  test    eax, eax
0x14001919d  jz      loc_1400192E7
0x1400191a3  cmp     qword ptr [rdi], 8
0x1400191a7  jnb     short loc_1400191B9
0x1400191a9  xor     ebx, ebx
0x1400191ab  lea     ecx, [rbx+18h]; dwErrCode
0x1400191ae  call    cs:__imp_SetLastError
0x1400191b4  jmp     loc_1400192E7
0x1400191b9  mov     eax, [rdi+24h]
0x1400191bc  lea     rax, ds:28h[rax*4]
0x1400191c4  cmp     [rdi], rax
0x1400191c7  jnz     short loc_1400191A9
0x1400191c9  movups  xmm0, xmmword ptr [rdi+10h]
0x1400191cd  lea     r8, [rbp+var_20]; struct _SU_POOL_OBJECT **
0x1400191d1  xor     edx, edx; unsigned int
0x1400191d3  lea     rcx, [rbp+InBuffer]; struct _GUID *
0x1400191d7  movdqu  xmmword ptr [rbp+InBuffer.Data1], xmm0
0x1400191dc  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x1400191e1  mov     rsi, [rbp+var_20]
0x1400191e5  mov     ebx, eax
0x1400191e7  test    eax, eax
0x1400191e9  jz      loc_1400192D9
0x1400191ef  mov     ecx, [rdi+24h]; unsigned int
0x1400191f2  lea     rdx, [rdi+28h]; unsigned int *
0x1400191f6  lea     r9, [rbp+var_30]; unsigned int **
0x1400191fa  lea     r8, [rbp+hMem]; struct _SP_DRIVE_INFO **
0x1400191fe  call    ?SuInitializeDriveTemplateList@@YAHIPEBKPEAPEAU_SP_DRIVE_INFO@@PEAPEAK@Z; SuInitializeDriveTemplateList(uint,ulong const *,_SP_DRIVE_INFO * *,ulong * *)
0x140019203  mov     ebx, eax
0x140019205  test    eax, eax
0x140019207  jz      loc_1400192B7
0x14001920d  mov     r9d, [rdi+24h]
0x140019211  mov     ecx, r9d; unsigned int
0x140019214  mov     rdx, [rbp+var_30]; unsigned int *
0x140019218  call    ?SuNumberOfErrors@@YAIIPEBK@Z; SuNumberOfErrors(uint,ulong const *)
0x14001921d  sub     r9d, eax
0x140019220  cmp     r9d, 1
0x140019224  jnb     short loc_140019236
0x140019226  xor     ebx, ebx
0x140019228  lea     ecx, [rbx+0Fh]; dwErrCode
0x14001922b  call    cs:__imp_SetLastError
0x140019231  jmp     loc_1400192B7
0x140019236  mov     ecx, 8081h
0x14001923b  call    IssueProgressStringResult
0x140019240  mov     ebx, eax
0x140019242  test    eax, eax
0x140019244  jz      short loc_1400192B7
0x140019246  mov     r9, [rbp+var_30]; unsigned int *
0x14001924a  mov     rcx, rsi; struct _SU_POOL_OBJECT *
0x14001924d  mov     r8, [rbp+hMem]; struct _SP_DRIVE_INFO *
0x140019251  mov     edx, [rdi+24h]; unsigned int
0x140019254  call    ?SuAddDrivesEx@@YAHPEAU_SU_POOL_OBJECT@@IPEAU_SP_DRIVE_INFO@@PEAK@Z; SuAddDrivesEx(_SU_POOL_OBJECT *,uint,_SP_DRIVE_INFO *,ulong *)
0x140019259  mov     ebx, eax
0x14001925b  test    eax, eax
0x14001925d  jz      short loc_1400192B7
0x14001925f  mov     r9d, [rdi+24h]
0x140019263  mov     ecx, r9d; unsigned int
0x140019266  mov     rdx, [rbp+var_30]; unsigned int *
0x14001926a  call    ?SuNumberOfErrors@@YAIIPEBK@Z; SuNumberOfErrors(uint,ulong const *)
0x14001926f  sub     r9d, eax
0x140019272  cmp     r9d, 1
0x140019276  jb      short loc_140019226
0x140019278  lea     rcx, [rsi+28h]; struct _GUID *
0x14001927c  mov     [r12], eax
0x140019280  call    ?SuAutoRepairSpaces@@YAXPEBU_GUID@@@Z; SuAutoRepairSpaces(_GUID const *)
0x140019285  cmp     dword ptr [rdi+20h], 0
0x140019289  jz      short loc_1400192B7
0x14001928b  mov     ecx, 8088h
0x140019290  call    IssueProgressStringResult
0x140019295  mov     ebx, eax
0x140019297  test    eax, eax
0x140019299  jz      short loc_1400192B7
0x14001929b  lea     rcx, [rbp+InBuffer]; lpInBuffer
0x14001929f  call    ?SuRebalancePool@@YAHPEAU_GUID@@@Z; SuRebalancePool(_GUID *)
0x1400192a4  mov     ebx, eax
0x1400192a6  test    eax, eax
0x1400192a8  jz      short loc_1400192B7
0x1400192aa  xor     edx, edx; bAlertable
0x1400192ac  mov     ecx, 3E8h; dwMilliseconds
0x1400192b1  call    cs:__imp_SleepEx
0x1400192b7  cmp     [rbp+hMem], 0
0x1400192bc  jz      short loc_1400192C8
0x1400192be  mov     rcx, [rbp+hMem]; hMem
0x1400192c2  call    cs:__imp_LocalFree
0x1400192c8  cmp     [rbp+var_30], 0
0x1400192cd  jz      short loc_1400192D9
0x1400192cf  mov     rcx, [rbp+var_30]; hMem
0x1400192d3  call    cs:__imp_LocalFree
0x1400192d9  test    rsi, rsi
0x1400192dc  jz      short loc_1400192E7
0x1400192de  mov     rcx, rsi; hMem
0x1400192e1  call    cs:__imp_LocalFree
0x1400192e7  mov     eax, ebx
0x1400192e9  mov     rcx, [rbp+var_8]
0x1400192ed  xor     rcx, rsp; StackCookie
0x1400192f0  call    __security_check_cookie
0x1400192f5  lea     r11, [rsp+50h+var_s0]
0x1400192fa  mov     rbx, [r11+30h]
0x1400192fe  mov     rsi, [r11+38h]
0x140019302  mov     rsp, r11
0x140019305  pop     r12
0x140019307  pop     rdi
0x140019308  pop     rbp
0x140019309  retn
```
