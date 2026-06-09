# GetAppDataFolderPathUnderUserProfile

- ea: `0x180069260`
- end: `0x1800696f4`
- name: `GetAppDataFolderPathUnderUserProfile`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180067814`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18005c398`
- `0x18005cb9c`
- `0x180069260`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcschr` at `0x180069644`
- `msvcrt!wcschr` at `0x180069644`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069365`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069365`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069334`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069334`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006931b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006931b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180069679`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180069679`
- `USERENV!GetProfilesDirectoryW` at `0x1800694e1`
- `USERENV!GetProfilesDirectoryW` at `0x1800694e1`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180069496`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180069496`

## pseudocode

```c
__int64 __fastcall GetAppDataFolderPathUnderUserProfile(__int64 *a1)
{
  struct _LIST_ENTRY *v2; // rbx
  DWORD v3; // edi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  DWORD SidFromToken; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int16 BasicProfileFolderPath; // ax
  __int64 v16; // r9
  WCHAR *v17; // rax
  unsigned __int64 v18; // r10
  unsigned int v19; // esi
  __int64 v20; // r8
  _WORD *v21; // rax
  wchar_t *v22; // rax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  DWORD cchSize; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h]
  _BYTE v28[528]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+250h] [rbp+150h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 767, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  memset_0(v28, 0, 0x20Au);
  memset_0(ProfileDir, 0, 0x20Au);
  cchSize = 0;
  TokenHandle = 0;
  hMem = 0;
  if ( a1 )
  {
    *a1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      goto LABEL_32;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
      {
        v8 = GetLastError();
        v6 = v8;
        if ( v8 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v6;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_16;
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 768, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
        }
        v9 = WPP_GLOBAL_Control;
LABEL_16:
        if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v9[1].Blink) >= 0 || BYTE1(v9[1].Blink) < 6u )
          return v6;
        v10 = 769;
        goto LABEL_20;
      }
LABEL_32:
      SidFromToken = GetSidFromToken(TokenHandle);
      v3 = SidFromToken;
      if ( SidFromToken )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_74;
        }
        v13 = 772;
        v14 = SidFromToken;
      }
      else
      {
        BasicProfileFolderPath = GetBasicProfileFolderPath(7, hMem, v28, 261);
        v3 = BasicProfileFolderPath;
        if ( BasicProfileFolderPath )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_74;
          }
          v13 = 773;
          v14 = BasicProfileFolderPath;
        }
        else
        {
          cchSize = 261;
          if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
          {
            v3 = GetLastError();
            goto LABEL_73;
          }
          v16 = 261;
          v17 = ProfileDir;
          do
          {
            if ( !*v17 )
              break;
            ++v17;
            --v16;
          }
          while ( v16 );
          v18 = (261 - v16) & -(__int64)(v16 != 0);
          v19 = v16 == 0 ? 0x57 : 0;
          if ( !v16 )
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 774, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v19);
              v2 = WPP_GLOBAL_Control;
            }
            v3 = v19;
            goto LABEL_74;
          }
          v20 = 261;
          v21 = v28;
          do
          {
            if ( !*v21 )
              break;
            ++v21;
            --v20;
          }
          while ( v20 );
          v3 = v20 == 0 ? 0x57 : 0;
          if ( v20 )
          {
            if ( ((261 - v20) & (unsigned __int64)-(__int64)(v20 != 0)) >= v18 + 1 )
            {
              if ( v18 < 0x104 )
              {
                v22 = wcschr((const wchar_t *)&v28[2 * v18 + 2], 0x5Cu);
                v23 = v22 + 1;
                if ( !v22 )
                  v23 = 0;
                v24 = StrDup(v23);
                *a1 = v24;
                if ( !v24 )
                  v3 = 8;
              }
              goto LABEL_73;
            }
            v3 = 10;
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_74;
            }
            v13 = 776;
          }
          else
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_74;
            }
            v13 = 775;
          }
          v14 = v3;
        }
      }
      WPP_SF_d(v2[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v14);
LABEL_73:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_74;
    }
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v6;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_28;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 770, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
    }
    v9 = WPP_GLOBAL_Control;
LABEL_28:
    if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v9[1].Blink) >= 0 || BYTE1(v9[1].Blink) < 6u )
      return v6;
    v10 = 771;
LABEL_20:
    WPP_SF_d(v9[1].Flink, v10, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v6);
    return v6;
  }
  v3 = 87;
LABEL_74:
  if ( hMem )
  {
    GlobalFree(hMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( TokenHandle != (void *)-1LL )
  {
    CloseHandle(TokenHandle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v2[1].Blink) < 0 && BYTE1(v2[1].Blink) >= 6u )
    WPP_SF_d(v2[1].Flink, 777, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180069260  mov     [rsp-8+arg_8], rbx
0x180069265  mov     [rsp-8+arg_10], rsi
0x18006926a  push    rbp
0x18006926b  push    rdi
0x18006926c  push    r13
0x18006926e  push    r14
0x180069270  push    r15
0x180069272  lea     rbp, [rsp-370h]
0x18006927a  sub     rsp, 470h
0x180069281  mov     rax, cs:__security_cookie
0x180069288  xor     rax, rsp
0x18006928b  mov     [rbp+390h+var_30], rax
0x180069292  mov     r14, rcx
0x180069295  mov     rbx, cs:WPP_GLOBAL_Control
0x18006929c  lea     r13, WPP_GLOBAL_Control
0x1800692a3  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800692aa  cmp     rbx, r13
0x1800692ad  jz      short loc_1800692D3
0x1800692af  test    byte ptr [rbx+1Ch], 80h
0x1800692b3  jz      short loc_1800692D3
0x1800692b5  cmp     byte ptr [rbx+19h], 6
0x1800692b9  jb      short loc_1800692D3
0x1800692bb  mov     rcx, [rbx+10h]
0x1800692bf  mov     edx, 2FFh
0x1800692c4  mov     r8, rsi
0x1800692c7  call    WPP_SF_
0x1800692cc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800692d3  mov     edi, 20Ah
0x1800692d8  lea     rcx, [rsp+490h+var_450]; void *
0x1800692dd  mov     r8d, edi; Size
0x1800692e0  xor     edx, edx; Val
0x1800692e2  call    memset_0
0x1800692e7  mov     r8d, edi; Size
0x1800692ea  lea     rcx, [rbp+390h+ProfileDir]; void *
0x1800692f1  xor     edx, edx; Val
0x1800692f3  call    memset_0
0x1800692f8  xor     r15d, r15d
0x1800692fb  mov     [rsp+490h+cchSize], r15d
0x180069300  mov     [rsp+490h+TokenHandle], r15
0x180069305  mov     [rsp+490h+hMem], r15
0x18006930a  test    r14, r14
0x18006930d  jnz     short loc_180069318
0x18006930f  lea     edi, [r15+57h]
0x180069313  jmp     loc_18006966F
0x180069318  mov     [r14], r15
0x18006931b  call    cs:__imp_GetCurrentThread
0x180069321  mov     edi, 0Ch
0x180069326  lea     r9, [rsp+490h+TokenHandle]; TokenHandle
0x18006932b  mov     rcx, rax; ThreadHandle
0x18006932e  mov     edx, edi; DesiredAccess
0x180069330  lea     r8d, [rdi-0Bh]; OpenAsSelf
0x180069334  call    cs:__imp_OpenThreadToken
0x18006933a  test    eax, eax
0x18006933c  jnz     loc_18006942D
0x180069342  call    cs:__imp_GetLastError
0x180069348  mov     ebx, eax
0x18006934a  cmp     eax, 3F0h
0x18006934f  jnz     loc_1800693DE
0x180069355  call    cs:__imp_GetCurrentProcess
0x18006935b  lea     r8, [rsp+490h+TokenHandle]; TokenHandle
0x180069360  mov     edx, edi; DesiredAccess
0x180069362  mov     rcx, rax; ProcessHandle
0x180069365  call    cs:__imp_OpenProcessToken
0x18006936b  test    eax, eax
0x18006936d  jnz     loc_18006942D
0x180069373  call    cs:__imp_GetLastError
0x180069379  mov     ebx, eax
0x18006937b  test    eax, eax
0x18006937d  jz      short loc_1800693AB
0x18006937f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069386  cmp     rcx, r13
0x180069389  jz      short loc_1800693D7
0x18006938b  test    byte ptr [rcx+1Ch], 80h
0x18006938f  jz      short loc_1800693B2
0x180069391  cmp     byte ptr [rcx+19h], 2
0x180069395  jb      short loc_1800693B2
0x180069397  mov     rcx, [rcx+10h]
0x18006939b  mov     edx, 300h
0x1800693a0  mov     r9d, eax
0x1800693a3  mov     r8, rsi
0x1800693a6  call    WPP_SF_d
0x1800693ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800693b2  cmp     rcx, r13
0x1800693b5  jz      short loc_1800693D7
0x1800693b7  test    byte ptr [rcx+1Ch], 80h
0x1800693bb  jz      short loc_1800693D7
0x1800693bd  cmp     byte ptr [rcx+19h], 6
0x1800693c1  jb      short loc_1800693D7
0x1800693c3  mov     edx, 301h
0x1800693c8  mov     rcx, [rcx+10h]
0x1800693cc  mov     r9d, ebx
0x1800693cf  mov     r8, rsi
0x1800693d2  call    WPP_SF_d
0x1800693d7  mov     eax, ebx
0x1800693d9  jmp     loc_1800696C9
0x1800693de  test    ebx, ebx
0x1800693e0  jz      short loc_18006940E
0x1800693e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800693e9  cmp     rcx, r13
0x1800693ec  jz      short loc_1800693D7
0x1800693ee  test    byte ptr [rcx+1Ch], 80h
0x1800693f2  jz      short loc_180069415
0x1800693f4  cmp     byte ptr [rcx+19h], 2
0x1800693f8  jb      short loc_180069415
0x1800693fa  mov     rcx, [rcx+10h]
0x1800693fe  mov     edx, 302h
0x180069403  mov     r9d, ebx
0x180069406  mov     r8, rsi
0x180069409  call    WPP_SF_d
0x18006940e  mov     rcx, cs:WPP_GLOBAL_Control
0x180069415  cmp     rcx, r13
0x180069418  jz      short loc_1800693D7
0x18006941a  test    byte ptr [rcx+1Ch], 80h
0x18006941e  jz      short loc_1800693D7
0x180069420  cmp     byte ptr [rcx+19h], 6
0x180069424  jb      short loc_1800693D7
0x180069426  mov     edx, 303h
0x18006942b  jmp     short loc_1800693C8
0x18006942d  mov     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x180069432  lea     rdx, [rsp+490h+hMem]
0x180069437  call    GetSidFromToken
0x18006943c  mov     edi, eax
0x18006943e  test    eax, eax
0x180069440  jz      short loc_18006947F
0x180069442  mov     rbx, cs:WPP_GLOBAL_Control
0x180069449  cmp     rbx, r13
0x18006944c  jz      loc_18006966F
0x180069452  test    byte ptr [rbx+1Ch], 80h
0x180069456  jz      loc_18006966F
0x18006945c  cmp     byte ptr [rbx+19h], 2
0x180069460  jb      loc_18006966F
0x180069466  mov     edx, 304h
0x18006946b  mov     r9d, eax
0x18006946e  mov     r8, rsi
0x180069471  mov     rcx, [rbx+10h]
0x180069475  call    WPP_SF_d
0x18006947a  jmp     loc_180069668
0x18006947f  mov     rdx, [rsp+490h+hMem]
0x180069484  lea     r8, [rsp+490h+var_450]
0x180069489  mov     ebx, 105h
0x18006948e  mov     ecx, 7
0x180069493  mov     r9d, ebx
0x180069496  call    cs:__imp_GetBasicProfileFolderPath
0x18006949c  movzx   edi, ax
0x18006949f  test    edi, edi
0x1800694a1  jz      short loc_1800694D1
0x1800694a3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800694aa  cmp     rbx, r13
0x1800694ad  jz      loc_18006966F
0x1800694b3  test    byte ptr [rbx+1Ch], 80h
0x1800694b7  jz      loc_18006966F
0x1800694bd  cmp     byte ptr [rbx+19h], 2
0x1800694c1  jb      loc_18006966F
0x1800694c7  mov     edx, 305h
0x1800694cc  mov     r9d, edi
0x1800694cf  jmp     short loc_18006946E
0x1800694d1  lea     rdx, [rsp+490h+cchSize]; lpcchSize
0x1800694d6  mov     [rsp+490h+cchSize], ebx
0x1800694da  lea     rcx, [rbp+390h+ProfileDir]; lpProfileDir
0x1800694e1  call    cs:__imp_GetProfilesDirectoryW
0x1800694e7  test    eax, eax
0x1800694e9  jnz     short loc_1800694F8
0x1800694eb  call    cs:__imp_GetLastError
0x1800694f1  mov     edi, eax
0x1800694f3  jmp     loc_180069668
0x1800694f8  mov     r9, rbx
0x1800694fb  lea     rax, [rbp+390h+ProfileDir]
0x180069502  cmp     [rax], r15w
0x180069506  jz      short loc_180069512
0x180069508  add     rax, 2
0x18006950c  sub     r9, 1
0x180069510  jnz     short loc_180069502
0x180069512  mov     rcx, rbx
0x180069515  mov     rax, r9
0x180069518  sub     rcx, r9
0x18006951b  mov     r8, r9
0x18006951e  neg     rax
0x180069521  mov     edi, 57h ; 'W'
0x180069526  mov     rax, r9
0x180069529  sbb     rdx, rdx
0x18006952c  and     rdx, rcx
0x18006952f  neg     r8
0x180069532  sbb     r10, r10
0x180069535  and     r10, rdx
0x180069538  neg     rax
0x18006953b  sbb     esi, esi
0x18006953d  not     esi
0x18006953f  and     esi, edi
0x180069541  test    r9, r9
0x180069544  jnz     short loc_180069584
0x180069546  mov     rbx, cs:WPP_GLOBAL_Control
0x18006954d  cmp     rbx, r13
0x180069550  jz      short loc_18006957D
0x180069552  test    byte ptr [rbx+1Ch], 80h
0x180069556  jz      short loc_18006957D
0x180069558  cmp     byte ptr [rbx+19h], 2
0x18006955c  jb      short loc_18006957D
0x18006955e  mov     rcx, [rbx+10h]
0x180069562  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069569  mov     edx, 306h
0x18006956e  mov     r9d, esi
0x180069571  call    WPP_SF_d
0x180069576  mov     rbx, cs:WPP_GLOBAL_Control
0x18006957d  mov     edi, esi
0x18006957f  jmp     loc_18006966F
0x180069584  mov     r8, rbx
0x180069587  lea     rax, [rsp+490h+var_450]
0x18006958c  cmp     [rax], r15w
0x180069590  jz      short loc_18006959C
0x180069592  add     rax, 2
0x180069596  sub     r8, 1
0x18006959a  jnz     short loc_18006958C
0x18006959c  sub     rbx, r8
0x18006959f  mov     rax, r8
0x1800695a2  neg     rax
0x1800695a5  mov     rdx, r8
0x1800695a8  mov     rax, r8
0x1800695ab  sbb     rcx, rcx
0x1800695ae  and     rcx, rbx
0x1800695b1  neg     rdx
0x1800695b4  sbb     r9, r9
0x1800695b7  and     r9, rcx
0x1800695ba  neg     rax
0x1800695bd  sbb     ecx, ecx
0x1800695bf  not     ecx
0x1800695c1  and     edi, ecx
0x1800695c3  test    r8, r8
0x1800695c6  jnz     short loc_180069600
0x1800695c8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800695cf  cmp     rbx, r13
0x1800695d2  jz      loc_18006966F
0x1800695d8  test    byte ptr [rbx+1Ch], 80h
0x1800695dc  jz      loc_18006966F
0x1800695e2  cmp     byte ptr [rbx+19h], 2
0x1800695e6  jb      loc_18006966F
0x1800695ec  mov     edx, 307h
0x1800695f1  mov     r9d, edi
0x1800695f4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800695fb  jmp     loc_180069471
0x180069600  lea     rax, [r10+1]
0x180069604  cmp     r9, rax
0x180069607  jnb     short loc_18006962D
0x180069609  mov     edi, 0Ah
0x18006960e  mov     rbx, cs:WPP_GLOBAL_Control
0x180069615  cmp     rbx, r13
0x180069618  jz      short loc_18006966F
0x18006961a  test    byte ptr [rbx+1Ch], 80h
0x18006961e  jz      short loc_18006966F
0x180069620  cmp     byte ptr [rbx+19h], 2
0x180069624  jb      short loc_18006966F
0x180069626  mov     edx, 308h
0x18006962b  jmp     short loc_1800695F1
0x18006962d  cmp     r10, 104h
0x180069634  jnb     short loc_180069668
0x180069636  lea     rcx, [rsp+490h+var_44E]
0x18006963b  mov     edx, 5Ch ; '\'; Ch
0x180069640  lea     rcx, [rcx+r10*2]; Str
0x180069644  call    cs:__imp_wcschr
0x18006964a  test    rax, rax
0x18006964d  lea     rcx, [rax+2]
0x180069651  cmovz   rcx, rax; pszSrc
0x180069655  call    StrDup
0x18006965a  test    rax, rax
0x18006965d  mov     [r14], rax
0x180069660  mov     ecx, 8
0x180069665  cmovz   edi, ecx
0x180069668  mov     rbx, cs:WPP_GLOBAL_Control
0x18006966f  mov     rcx, [rsp+490h+hMem]; hMem
0x180069674  test    rcx, rcx
0x180069677  jz      short loc_180069686
0x180069679  call    cs:__imp_GlobalFree
0x18006967f  mov     rbx, cs:WPP_GLOBAL_Control
0x180069686  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x18006968b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006968f  jz      short loc_18006969E
0x180069691  call    cs:__imp_CloseHandle
0x180069697  mov     rbx, cs:WPP_GLOBAL_Control
0x18006969e  cmp     rbx, r13
0x1800696a1  jz      short loc_1800696C7
0x1800696a3  test    byte ptr [rbx+1Ch], 80h
0x1800696a7  jz      short loc_1800696C7
0x1800696a9  cmp     byte ptr [rbx+19h], 6
0x1800696ad  jb      short loc_1800696C7
0x1800696af  mov     rcx, [rbx+10h]
0x1800696b3  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800696ba  mov     edx, 309h
0x1800696bf  mov     r9d, edi
0x1800696c2  call    WPP_SF_d
0x1800696c7  mov     eax, edi
0x1800696c9  mov     rcx, [rbp+390h+var_30]
0x1800696d0  xor     rcx, rsp; StackCookie
0x1800696d3  call    __security_check_cookie
0x1800696d8  lea     r11, [rsp+490h+var_20]
0x1800696e0  mov     rbx, [r11+38h]
0x1800696e4  mov     rsi, [r11+40h]
0x1800696e8  mov     rsp, r11
0x1800696eb  pop     r15
0x1800696ed  pop     r14
0x1800696ef  pop     r13
0x1800696f1  pop     rdi
  ... truncated ...
```
