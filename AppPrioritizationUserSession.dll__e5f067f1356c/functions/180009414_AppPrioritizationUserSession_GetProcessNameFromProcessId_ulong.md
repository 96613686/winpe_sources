# AppPrioritizationUserSession::GetProcessNameFromProcessId(ulong)

- ea: `0x180009414`
- end: `0x18000976b`
- name: `?GetProcessNameFromProcessId@AppPrioritizationUserSession@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `855`
- prototype: `_OWORD *__fastcall(__int64, DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180009a30`

## callees

- `0x180001304`
- `0x180002650`
- `0x1800032a4`
- `0x1800080c0`
- `0x180008458`
- `0x18000887c`
- `0x180009414`
- `0x18000ae64`
- `0x18000af14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000947a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000947a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000950e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000950e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009730`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009452`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009452`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000954b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000954b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall AppPrioritizationUserSession::GetProcessNameFromProcessId(__int64 a1, DWORD a2)
{
  char *v4; // rax
  char *v5; // rbx
  _OWORD *result; // rax
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 last_of; // rax
  __int64 v10; // rcx
  __int128 *v11; // rax
  _OWORD *v12; // rdx
  char v13; // si
  char v14; // si
  _OWORD *v15; // rcx
  DWORD v16; // [rsp+30h] [rbp-2E8h] BYREF
  DWORD LastError; // [rsp+34h] [rbp-2E4h] BYREF
  _OWORD *v18; // [rsp+38h] [rbp-2E0h]
  int v19; // [rsp+40h] [rbp-2D8h]
  _OWORD v20[2]; // [rsp+48h] [rbp-2D0h] BYREF
  char *v21; // [rsp+68h] [rbp-2B0h]
  DWORD dwSize; // [rsp+70h] [rbp-2A8h] BYREF
  __int128 v23; // [rsp+78h] [rbp-2A0h] BYREF
  __int128 v24; // [rsp+88h] [rbp-290h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+A0h] [rbp-278h] BYREF
  DWORD *v26; // [rsp+C0h] [rbp-258h]
  __int64 v27; // [rsp+C8h] [rbp-250h]
  DWORD *p_LastError; // [rsp+D0h] [rbp-248h]
  __int64 v29; // [rsp+D8h] [rbp-240h]
  WCHAR ExeName[264]; // [rsp+E0h] [rbp-238h] BYREF

  v18 = (_OWORD *)a1;
  v19 = 0;
  v4 = (char *)OpenProcess(0x1010u, 0, a2);
  try
  {
    v5 = v4;
    v21 = v4;
    if ( ((unsigned __int64)(v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      memset_0(ExeName, 0, 0x208u);
      dwSize = 260;
      if ( QueryFullProcessImageNameW(v5, 0, ExeName, &dwSize) )
      {
        v23 = 0;
        v24 = 0;
        v7 = -1;
        v8 = -1;
        do
          ++v8;
        while ( ExeName[v8] );
        std::wstring::_Construct<1,unsigned short const *>(&v23, ExeName, v8);
        last_of = std::wstring::find_last_of(&v23);
        if ( last_of == -1 )
        {
          v12 = (_OWORD *)std::wstring::wstring(&v25, &v23);
          v13 = 4;
        }
        else
        {
          v10 = last_of + 1;
          memset(v20, 0, sizeof(v20));
          if ( (unsigned __int64)v24 < last_of + 1 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
          if ( (_QWORD)v24 - v10 != -1 )
            v7 = v24 - v10;
          v11 = &v23;
          if ( *((_QWORD *)&v24 + 1) > 7u )
            v11 = (__int128 *)v23;
          std::wstring::_Construct<1,unsigned short const *>(v20, (char *)v11 + 2 * v10, v7);
          v12 = v20;
          v13 = 10;
        }
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        *(_OWORD *)a1 = *v12;
        *(_OWORD *)(a1 + 16) = v12[1];
        *(_WORD *)v12 = 0;
        *((_QWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 3) = 7;
        v14 = v13 | 1;
        if ( (v14 & 4) != 0 )
        {
          v14 &= ~4u;
          std::wstring::~wstring(&v25);
        }
        if ( (v14 & 2) != 0 )
          std::wstring::~wstring(v20);
        std::wstring::~wstring(&v23);
        CloseHandle(v5);
        result = (_OWORD *)a1;
      }
      else
      {
        if ( (unsigned int)dword_180014000 > 2 )
        {
          LastError = GetLastError();
          v16 = a2;
          p_LastError = &LastError;
          v29 = 4;
          v26 = &v16;
          v27 = 4;
          tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&byte_18000FD73, 0, 0, 4u, &v25);
        }
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        std::wstring::_Construct<1,unsigned short const *>(a1, &dword_18000EE34, 0);
        CloseHandle(v5);
        result = (_OWORD *)a1;
      }
    }
    else
    {
      if ( (unsigned int)dword_180014000 > 2 )
      {
        v16 = GetLastError();
        LastError = a2;
        p_LastError = &v16;
        v29 = 4;
        v26 = &LastError;
        v27 = 4;
        tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&dword_18000FDEC, 0, 0, 4u, &v25);
      }
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      std::wstring::_Construct<1,unsigned short const *>(a1, &dword_18000EE34, 0);
      if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v5);
      result = (_OWORD *)a1;
    }
  }
  catch ( ... )
  {
    v15 = v18;
    *v18 = 0;
    *((_QWORD *)v15 + 2) = 0;
    *((_QWORD *)v15 + 3) = 0;
    std::wstring::_Construct<1,unsigned short const *>(v15, &dword_18000EE34, 0);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x180009414  mov     [rsp+arg_10], rbx
0x180009419  push    rsi
0x18000941a  push    rdi
0x18000941b  push    r14
0x18000941d  sub     rsp, 300h
0x180009424  mov     rax, cs:__security_cookie
0x18000942b  xor     rax, rsp
0x18000942e  mov     [rsp+318h+var_28], rax
0x180009436  mov     esi, edx
0x180009438  mov     rdi, rcx
0x18000943b  mov     [rsp+318h+var_2E0], rcx
0x180009440  xor     r14d, r14d
0x180009443  mov     [rsp+318h+var_2D8], r14d
0x180009448  mov     r8d, edx; dwProcessId
0x18000944b  xor     edx, edx; bInheritHandle
0x18000944d  mov     ecx, 1010h; dwDesiredAccess
0x180009452  call    cs:__imp_OpenProcess
0x180009458  mov     rbx, rax
0x18000945b  mov     [rsp+318h+var_2B0], rax
0x180009460  inc     rax
0x180009463  test    rax, 0FFFFFFFFFFFFFFFEh
0x180009469  jnz     loc_18000951C
0x18000946f  mov     eax, cs:dword_180014000
0x180009475  cmp     eax, 2
0x180009478  jbe     short loc_1800094E0
0x18000947a  call    cs:__imp_GetLastError
0x180009480  mov     [rsp+318h+var_2E8], eax
0x180009484  mov     [rsp+318h+var_2E4], esi
0x180009488  lea     rax, [rsp+318h+var_2E8]
0x18000948d  mov     [rsp+318h+var_248], rax
0x180009495  lea     ecx, [r14+4]
0x180009499  mov     [rsp+318h+var_240], rcx
0x1800094a1  lea     rax, [rsp+318h+var_2E4]
0x1800094a6  mov     [rsp+318h+var_258], rax
0x1800094ae  mov     [rsp+318h+var_250], rcx
0x1800094b6  lea     rax, [rsp+318h+var_278]
0x1800094be  mov     [rsp+318h+var_2F0], rax; PEVENT_DATA_DESCRIPTOR
0x1800094c3  mov     [rsp+318h+var_2F8], ecx; ULONG
0x1800094c7  xor     r9d, r9d; int
0x1800094ca  xor     r8d, r8d; int
0x1800094cd  lea     rdx, dword_18000FDEC; int
0x1800094d4  lea     rcx, dword_180014000; int
0x1800094db  call    _tlgWriteTransfer_EventWriteTransfer
0x1800094e0  xorps   xmm0, xmm0
0x1800094e3  movups  xmmword ptr [rdi], xmm0
0x1800094e6  mov     [rdi+10h], r14
0x1800094ea  mov     [rdi+18h], r14
0x1800094ee  xor     r8d, r8d
0x1800094f1  lea     rdx, dword_18000EE34
0x1800094f8  mov     rcx, rdi
0x1800094fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009500  nop
0x180009501  lea     rcx, [rbx-1]
0x180009505  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180009509  ja      short loc_180009514
0x18000950b  mov     rcx, rbx; hObject
0x18000950e  call    cs:__imp_CloseHandle
0x180009514  mov     rax, rdi
0x180009517  jmp     loc_180009740
0x18000951c  xor     edx, edx; Val
0x18000951e  mov     r8d, 208h; Size
0x180009524  lea     rcx, [rsp+318h+ExeName]; void *
0x18000952c  call    memset_0
0x180009531  mov     [rsp+318h+dwSize], 104h
0x180009539  lea     r9, [rsp+318h+dwSize]; lpdwSize
0x18000953e  lea     r8, [rsp+318h+ExeName]; lpExeName
0x180009546  xor     edx, edx; dwFlags
0x180009548  mov     rcx, rbx; hProcess
0x18000954b  call    cs:__imp_QueryFullProcessImageNameW
0x180009551  test    eax, eax
0x180009553  jz      loc_18000969A
0x180009559  xorps   xmm0, xmm0
0x18000955c  movups  [rsp+318h+var_2A0], xmm0
0x180009561  xorps   xmm1, xmm1
0x180009564  movdqu  [rsp+318h+var_290], xmm1
0x18000956d  lea     rax, [rsp+318h+ExeName]
0x180009575  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009579  mov     r8, rsi
0x18000957c  inc     r8
0x18000957f  cmp     [rax+r8*2], r14w
0x180009584  jnz     short loc_18000957C
0x180009586  lea     rdx, [rsp+318h+ExeName]
0x18000958e  lea     rcx, [rsp+318h+var_2A0]
0x180009593  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009598  nop
0x180009599  lea     rcx, [rsp+318h+var_2A0]
0x18000959e  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800095a3  cmp     rax, rsi
0x1800095a6  jz      short loc_18000960C
0x1800095a8  lea     rcx, [rax+1]
0x1800095ac  xorps   xmm0, xmm0
0x1800095af  movups  [rsp+318h+var_2D0], xmm0
0x1800095b4  xorps   xmm1, xmm1
0x1800095b7  movdqu  [rsp+318h+var_2C0], xmm1
0x1800095bd  mov     rax, qword ptr [rsp+318h+var_290]
0x1800095c5  cmp     rax, rcx
0x1800095c8  jb      loc_180009764
0x1800095ce  sub     rax, rcx
0x1800095d1  cmp     rax, rsi
0x1800095d4  cmovb   rsi, rax
0x1800095d8  lea     rax, [rsp+318h+var_2A0]
0x1800095dd  cmp     qword ptr [rsp+318h+var_290+8], 7
0x1800095e6  cmova   rax, qword ptr [rsp+318h+var_2A0]
0x1800095ec  lea     rdx, [rax+rcx*2]
0x1800095f0  mov     r8, rsi
0x1800095f3  lea     rcx, [rsp+318h+var_2D0]
0x1800095f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800095fd  lea     rdx, [rsp+318h+var_2D0]
0x180009602  mov     esi, 0Ah
0x180009607  lea     ecx, [rsi-6]
0x18000960a  jmp     short loc_180009628
0x18000960c  lea     rdx, [rsp+318h+var_2A0]
0x180009611  lea     rcx, [rsp+318h+var_278]
0x180009619  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000961e  mov     rdx, rax
0x180009621  mov     ecx, 4
0x180009626  mov     esi, ecx
0x180009628  xorps   xmm0, xmm0
0x18000962b  movups  xmmword ptr [rdi], xmm0
0x18000962e  mov     [rdi+10h], r14
0x180009632  mov     [rdi+18h], r14
0x180009636  movups  xmm0, xmmword ptr [rdx]
0x180009639  movups  xmmword ptr [rdi], xmm0
0x18000963c  movups  xmm1, xmmword ptr [rdx+10h]
0x180009640  movups  xmmword ptr [rdi+10h], xmm1
0x180009644  mov     [rdx], r14w
0x180009648  mov     [rdx+10h], r14
0x18000964c  mov     qword ptr [rdx+18h], 7
0x180009654  or      esi, 1
0x180009657  test    cl, sil
0x18000965a  jz      short loc_18000966D
0x18000965c  and     esi, 0FFFFFFFBh
0x18000965f  lea     rcx, [rsp+318h+var_278]
0x180009667  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000966c  nop
0x18000966d  test    sil, 2
0x180009671  jz      short loc_18000967E
0x180009673  lea     rcx, [rsp+318h+var_2D0]
0x180009678  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000967d  nop
0x18000967e  lea     rcx, [rsp+318h+var_2A0]
0x180009683  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009688  nop
0x180009689  mov     rcx, rbx; hObject
0x18000968c  call    cs:__imp_CloseHandle
0x180009692  mov     rax, rdi
0x180009695  jmp     loc_180009740
0x18000969a  mov     eax, cs:dword_180014000
0x1800096a0  cmp     eax, 2
0x1800096a3  jbe     short loc_18000970C
0x1800096a5  call    cs:__imp_GetLastError
0x1800096ab  mov     [rsp+318h+var_2E4], eax
0x1800096af  mov     [rsp+318h+var_2E8], esi
0x1800096b3  lea     rax, [rsp+318h+var_2E4]
0x1800096b8  mov     [rsp+318h+var_248], rax
0x1800096c0  mov     ecx, 4
0x1800096c5  mov     [rsp+318h+var_240], rcx
0x1800096cd  lea     rax, [rsp+318h+var_2E8]
0x1800096d2  mov     [rsp+318h+var_258], rax
0x1800096da  mov     [rsp+318h+var_250], rcx
0x1800096e2  lea     rax, [rsp+318h+var_278]
0x1800096ea  mov     [rsp+318h+var_2F0], rax; PEVENT_DATA_DESCRIPTOR
0x1800096ef  mov     [rsp+318h+var_2F8], ecx; ULONG
0x1800096f3  xor     r9d, r9d; int
0x1800096f6  xor     r8d, r8d; int
0x1800096f9  lea     rdx, byte_18000FD73; int
0x180009700  lea     rcx, dword_180014000; int
0x180009707  call    _tlgWriteTransfer_EventWriteTransfer
0x18000970c  xorps   xmm0, xmm0
0x18000970f  movups  xmmword ptr [rdi], xmm0
0x180009712  mov     [rdi+10h], r14
0x180009716  mov     [rdi+18h], r14
0x18000971a  xor     r8d, r8d
0x18000971d  lea     rdx, dword_18000EE34
0x180009724  mov     rcx, rdi
0x180009727  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000972c  nop
0x18000972d  mov     rcx, rbx; hObject
0x180009730  call    cs:__imp_CloseHandle
0x180009736  mov     rax, rdi
0x180009739  jmp     short loc_180009740
0x18000973b  mov     rax, [rsp+318h+var_2E0]
0x180009740  mov     rcx, [rsp+318h+var_28]
0x180009748  xor     rcx, rsp; StackCookie
0x18000974b  call    __security_check_cookie
0x180009750  mov     rbx, [rsp+318h+arg_10]
0x180009758  add     rsp, 300h
0x18000975f  pop     r14
0x180009761  pop     rdi
0x180009762  pop     rsi
0x180009763  retn
0x180009764  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
