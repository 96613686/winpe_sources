# StartAddress

- ea: `0x1800c8c70`
- end: `0x1800c921c`
- name: `StartAddress`
- size: `1452`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180073ef4`
- `0x180073f30`
- `0x180087788`
- `0x180094ea8`
- `0x180095a14`
- `0x180096190`
- `0x18009674c`
- `0x180096834`
- `0x180098d54`
- `0x1800ba998`
- `0x1800bacec`
- `0x1800c87ac`
- `0x1800c8a60`
- `0x1800c8c70`
- `0x1800c9220`
- `0x1800d83ec`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800c8cdd`
- `KERNEL32!GetTickCount` at `0x1800c8e5e`
- `KERNEL32!GetTickCount` at `0x1800c8f1a`
- `KERNEL32!GetTickCount` at `0x1800c8cdd`
- `KERNEL32!GetTickCount` at `0x1800c8e5e`
- `KERNEL32!GetTickCount` at `0x1800c8f1a`
- `KERNEL32!EnterCriticalSection` at `0x1800c8cd2`
- `KERNEL32!EnterCriticalSection` at `0x1800c8eb1`
- `KERNEL32!EnterCriticalSection` at `0x1800c8f3b`
- `KERNEL32!EnterCriticalSection` at `0x1800c9113`
- `KERNEL32!EnterCriticalSection` at `0x1800c8cd2`
- `KERNEL32!EnterCriticalSection` at `0x1800c8eb1`
- `KERNEL32!EnterCriticalSection` at `0x1800c8f3b`
- `KERNEL32!EnterCriticalSection` at `0x1800c9113`
- `KERNEL32!LeaveCriticalSection` at `0x1800c8d7f`
- `KERNEL32!LeaveCriticalSection` at `0x1800c9071`
- `KERNEL32!LeaveCriticalSection` at `0x1800c90fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800c912d`
- `KERNEL32!LeaveCriticalSection` at `0x1800c8d7f`
- `KERNEL32!LeaveCriticalSection` at `0x1800c9071`
- `KERNEL32!LeaveCriticalSection` at `0x1800c90fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800c912d`
- `KERNEL32!CloseHandle` at `0x1800c91ed`
- `KERNEL32!CloseHandle` at `0x1800c91ed`
- `KERNEL32!GetLastError` at `0x1800c8dc6`
- `KERNEL32!GetLastError` at `0x1800c8dc6`
- `KERNEL32!WaitForSingleObject` at `0x1800c8db6`
- `KERNEL32!WaitForSingleObject` at `0x1800c8db6`
- `KERNEL32!GetCurrentThreadId` at `0x1800c8cc6`
- `KERNEL32!GetCurrentThreadId` at `0x1800c8cc6`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800c919f`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800c91c4`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800c919f`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800c91c4`
- `Mso20Win32Client!Mso20Win32Client_62300` at `0x1800c8dac`
- `Mso20Win32Client!Mso20Win32Client_62300` at `0x1800c8dac`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StartAddress(struct _RTL_CRITICAL_SECTION *lpThreadParameter)
{
  struct _RTL_CRITICAL_SECTION *v1; // r13
  struct _RTL_CRITICAL_SECTION *i; // rbx
  __int64 v3; // rsi
  DWORD v4; // edi
  __int64 v5; // rcx
  DWORD TickCount; // r12d
  __int64 v7; // r14
  unsigned int v8; // r15d
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // r12d
  __int64 v14; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  DWORD v16; // eax
  __int64 v17; // rcx
  DWORD LastError; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int *v26; // rax
  unsigned int DebugInfo_high; // ecx
  unsigned int v28; // edi
  unsigned int LockCount; // eax
  unsigned int v30; // r15d
  unsigned int v31; // r14d
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r14
  int v39; // r15d
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rcx
  unsigned int v45; // [rsp+30h] [rbp-89h]
  DWORD v46; // [rsp+34h] [rbp-85h]
  unsigned int v47; // [rsp+38h] [rbp-81h]
  __int64 v48; // [rsp+40h] [rbp-79h]
  _DWORD v49[10]; // [rsp+48h] [rbp-71h] BYREF
  _DWORD v50[2]; // [rsp+70h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-41h] BYREF
  _DWORD v52[10]; // [rsp+80h] [rbp-39h] BYREF
  _DWORD v53[26]; // [rsp+A8h] [rbp-11h] BYREF
  DWORD CurrentThreadId; // [rsp+128h] [rbp+6Fh]
  unsigned int v56; // [rsp+128h] [rbp+6Fh]
  int v57; // [rsp+130h] [rbp+77h]
  unsigned int v58; // [rsp+138h] [rbp+7Fh]

  v1 = lpThreadParameter;
  v53[0] = 1;
  v53[8] = 0;
  sub_1800D83EC(&hObject, 0, v53);
  for ( i = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 56); ; i = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 56) )
  {
    while ( 1 )
    {
      v49[0] = 1;
      v49[8] = 0;
      v3 = 0;
      v48 = 0;
      v4 = 0;
      CurrentThreadId = GetCurrentThreadId();
      while ( 1 )
      {
        EnterCriticalSection(i);
        sub_1800C9220(v5);
        TickCount = GetTickCount();
        v7 = 0;
        v8 = 0;
        if ( HIDWORD(i[1].OwningThread) )
        {
          do
          {
            v9 = *(_QWORD *)&i[1].LockCount;
            v10 = *(_QWORD *)(v9 + 8LL * v8);
            v11 = *(_DWORD *)(v10 + 16);
            if ( v11 == CurrentThreadId )
            {
              *(_DWORD *)(v10 + 16) = 0;
              v11 = 0;
            }
            if ( *(_DWORD *)(v10 + 4) <= TickCount )
            {
              v3 = v10;
              v48 = v10;
              sub_180073EF4(&v1[2].LockSemaphore, v10);
              i = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 56);
              goto LABEL_16;
            }
            if ( !v11 )
            {
              if ( !v7 || (sub_1800C9220(v9), (unsigned int)(*(_DWORD *)(v7 + 4) - *(_DWORD *)(v10 + 4)) < 0x80000000) )
                v7 = v10;
            }
            ++v8;
            i = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 56);
          }
          while ( v8 < HIDWORD(v1[2].SpinCount) );
          if ( !v7 )
            goto LABEL_15;
          v4 = *(_DWORD *)(v7 + 4) - TickCount;
          *(_DWORD *)(v7 + 16) = CurrentThreadId;
        }
        else
        {
LABEL_15:
          v4 = -1;
        }
LABEL_16:
        LeaveCriticalSection(i);
        v13 = 0;
        if ( v3 )
          break;
        v14 = sub_1800C9220(v12);
        DebugInfo = i[1].DebugInfo;
        if ( *(_DWORD *)(v14 + 344) )
        {
          v50[0] = v4;
          v50[1] = v4;
          v16 = Mso20Win32Client_62300(DebugInfo, v50, 0);
        }
        else
        {
          v16 = WaitForSingleObject(DebugInfo, v4);
        }
        if ( v16 == -1 )
        {
          sub_1800C9220(v17);
          LastError = GetLastError();
          sub_1800C87AC(v19, v49, LastError);
        }
        v20 = v49[0];
        if ( (v49[0] & 8) != 0 )
        {
          v3 = 0;
          v48 = 0;
          goto LABEL_25;
        }
      }
      v20 = v49[0];
LABEL_25:
      if ( (v20 & 8) == 0 )
        break;
      if ( (v20 & 0xFFFFFFFE) != 0 )
        sub_180098D54(v49);
    }
    if ( !*(_DWORD *)v3 )
      break;
    switch ( *(_DWORD *)v3 )
    {
      case 1:
        if ( !*(_DWORD *)(sub_1800C9220((unsigned int)(*(_DWORD *)v3 - 1)) + 320) )
          sub_180094EA8(
            *(_QWORD *)(v3 + 8),
            (unsigned int)&hObject,
            *(_DWORD *)(v3 + 20),
            *(_DWORD *)(v3 + 24),
            (__int64)v49);
        goto LABEL_77;
      case 2:
        goto LABEL_74;
      case 3:
        v42 = *(_QWORD *)(v3 + 8);
        EnterCriticalSection(v1 + 7);
        LODWORD(v42) = sub_180073F30(&v1[6].LockSemaphore, v42);
        LeaveCriticalSection(v1 + 7);
        if ( (_DWORD)v42 )
          sub_180087788(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 104LL));
        goto LABEL_77;
    }
    v21 = (unsigned int)(*(_DWORD *)v3 - 4);
    if ( *(_DWORD *)v3 != 4 )
    {
      if ( *(_DWORD *)v3 != 5 )
        goto LABEL_78;
      v22 = *(_QWORD *)(v3 + 8);
      *(_DWORD *)(v22 + 312) = 0;
      v23 = *(_DWORD *)(v22 + 308);
      if ( !v23 )
        goto LABEL_38;
      sub_1800C9220(v21);
      sub_1800C9220(v24);
      v25 = v23 - GetTickCount();
      if ( (unsigned int)v25 < 0x80000000 )
      {
        *(_DWORD *)(v3 + 4) = v23;
        v26 = (unsigned int *)sub_1800C9220(v25);
        sub_1800C8A60(v26, v3, (__int64)v49);
        if ( (v49[0] & 8) == 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v22 + 368));
          *(_DWORD *)(v22 + 312) = v23;
        }
LABEL_38:
        _InterlockedDecrement((volatile signed __int32 *)(v22 + 368));
        goto LABEL_78;
      }
LABEL_74:
      sub_180095A14(*(_QWORD *)(v3 + 8), v49, 0);
      sub_180096190(*(_QWORD *)(v3 + 8), v49);
LABEL_77:
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v3 + 8) + 368LL));
      goto LABEL_78;
    }
    EnterCriticalSection(v1 + 7);
    DebugInfo_high = HIDWORD(v1[6].DebugInfo);
    v28 = DebugInfo_high / 0xA;
    LockCount = v1[6].LockCount;
    if ( LockCount > DebugInfo_high )
      v28 += LockCount - DebugInfo_high;
    if ( v28 )
    {
      v30 = 0;
      v56 = 0;
      v31 = 0;
      v57 = 0;
      if ( HIDWORD(v1[6].SpinCount) )
      {
        while ( 1 )
        {
          v52[0] = 1;
          v52[8] = 0;
          v32 = *((_QWORD *)v1[6].LockSemaphore + v31);
          sub_1800C9220(v31);
          v46 = GetTickCount();
          v45 = *(_DWORD *)(v32 + 320) + ((v46 - *(_DWORD *)(v32 + 320)) >> 1);
          EnterCriticalSection((LPCRITICAL_SECTION)(v32 + 160));
          v33 = (unsigned int)(17 * *(_DWORD *)(v32 + 264));
          v47 = v33;
          v58 = 0;
          if ( (_DWORD)v33 )
          {
            do
            {
              if ( v13 >= v28 )
                break;
              v34 = (unsigned int)(*(_DWORD *)(v32 + 384) + 1);
              *(_DWORD *)(v32 + 384) = v34;
              if ( (unsigned int)v34 >= (unsigned int)v33 )
              {
                sub_1800C9220(v33);
                v35 = *(_DWORD *)(v32 + 324);
                if ( v46 - v35 < 0x80000000 )
                  *(_DWORD *)(v32 + 320) = v35;
                *(_DWORD *)(v32 + 324) = v46 + 86400000;
                *(_DWORD *)(v32 + 384) = 0;
                v34 = 0;
              }
              v36 = sub_180096834(v32, v34);
              v38 = v36;
              if ( v36 && !*(_WORD *)(v36 + 212) )
              {
                v39 = *(_DWORD *)(v36 + 208);
                sub_1800C9220(v37);
                v40 = v45 - v39;
                if ( (unsigned int)v40 >= 0x80000000 )
                {
                  if ( (*(_DWORD *)(v38 + 56) & 7u) <= 2
                    || (v40 = *(unsigned int *)(v38 + 16LL * *(int *)(v38 + 48) + 56),
                        LOBYTE(v40) = v40 & 7,
                        (unsigned __int8)v40 <= 2u) )
                  {
                    sub_1800C9220(v40);
                    if ( (unsigned int)(*(_DWORD *)(v32 + 324) - v39) < 0x80000000 )
                      *(_DWORD *)(v32 + 324) = v39;
                  }
                }
                else
                {
                  v13 += sub_1800BA998(v38, v52);
                }
                sub_1800BACEC(v38);
              }
              ++v58;
              v33 = v47;
            }
            while ( v58 < v47 );
            v3 = v48;
            v1 = lpThreadParameter;
            if ( v13 )
              sub_18009674C(v32);
            v30 = v56;
            v31 = v57;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 160));
          v30 += v13;
          v56 = v30;
          sub_180095A14(v32, v52, 0);
          v41 = v52[0];
          if ( (v52[0] & 8) != 0 )
          {
            sub_180096190(v32, v52);
            v41 = v52[0];
          }
          if ( v30 >= v28 )
            break;
          v28 -= v30;
          if ( (v41 & 0xFFFFFFFE) != 0 )
            sub_180098D54(v52);
          v57 = ++v31;
          v13 = 0;
          if ( v31 >= HIDWORD(v1[6].SpinCount) )
            goto LABEL_71;
        }
        if ( (v41 & 0xFFFFFFFE) != 0 )
          sub_180098D54(v52);
      }
    }
LABEL_71:
    LODWORD(v1[8].DebugInfo) = 0;
    LeaveCriticalSection(v1 + 7);
LABEL_78:
    Mso20Win32Client_53248(v3);
    if ( (v49[0] & 0xFFFFFFFE) != 0 )
      sub_180098D54(v49);
  }
  Mso20Win32Client_53248(v3);
  _InterlockedDecrement((volatile signed __int32 *)(sub_1800C9220(v43) + 332));
  if ( (v49[0] & 0xFFFFFFFE) != 0 )
    sub_180098D54(v49);
  CloseHandle(hObject);
  if ( (v53[0] & 0xFFFFFFFE) != 0 )
    sub_180098D54(v53);
  return 0;
}

```

## disassembly

```asm
0x1800c8c70  mov     [rsp-8+arg_0], rcx
0x1800c8c75  push    rbp
0x1800c8c76  push    rbx
0x1800c8c77  push    rsi
0x1800c8c78  push    rdi
0x1800c8c79  push    r12
0x1800c8c7b  push    r13
0x1800c8c7d  push    r14
0x1800c8c7f  push    r15
0x1800c8c81  lea     rbp, [rsp-1Fh]
0x1800c8c86  sub     rsp, 0D8h
0x1800c8c8d  mov     r13, rcx
0x1800c8c90  mov     [rbp+57h+var_68], 1
0x1800c8c97  xor     r12d, r12d
0x1800c8c9a  mov     [rbp+57h+var_48], r12d
0x1800c8c9e  lea     r8, [rbp+57h+var_68]
0x1800c8ca2  xor     edx, edx
0x1800c8ca4  lea     rcx, [rbp+57h+hObject]
0x1800c8ca8  call    sub_1800D83EC
0x1800c8cad  lea     rbx, [r13+38h]
0x1800c8cb1  mov     [rbp+57h+var_C8], 1
0x1800c8cb8  mov     [rbp+57h+var_A8], r12d
0x1800c8cbc  mov     rsi, r12
0x1800c8cbf  mov     [rbp+57h+var_D0], r12
0x1800c8cc3  mov     edi, r12d
0x1800c8cc6  call    cs:GetCurrentThreadId
0x1800c8ccc  mov     [rbp+57h+arg_8], eax
0x1800c8ccf  mov     rcx, rbx; lpCriticalSection
0x1800c8cd2  call    cs:EnterCriticalSection
0x1800c8cd8  call    sub_1800C9220
0x1800c8cdd  call    cs:GetTickCount
0x1800c8ce3  mov     r12d, eax
0x1800c8ce6  xor     r8d, r8d
0x1800c8ce9  mov     r14d, r8d
0x1800c8cec  mov     r15d, r8d
0x1800c8cef  cmp     [rbx+3Ch], r8d
0x1800c8cf3  jbe     loc_1800C8D79
0x1800c8cf9  mov     edx, r15d
0x1800c8cfc  mov     rcx, [rbx+30h]
0x1800c8d00  mov     rbx, [rcx+rdx*8]
0x1800c8d04  mov     eax, [rbx+10h]
0x1800c8d07  cmp     eax, [rbp+57h+arg_8]
0x1800c8d0a  jnz     short loc_1800C8D13
0x1800c8d0c  mov     [rbx+10h], r8d
0x1800c8d10  mov     eax, r8d
0x1800c8d13  cmp     [rbx+4], r12d
0x1800c8d17  jbe     short loc_1800C8D60
0x1800c8d19  test    eax, eax
0x1800c8d1b  jnz     short loc_1800C8D38
0x1800c8d1d  test    r14, r14
0x1800c8d20  jz      short loc_1800C8D35
0x1800c8d22  call    sub_1800C9220
0x1800c8d27  mov     eax, [r14+4]
0x1800c8d2b  sub     eax, [rbx+4]
0x1800c8d2e  cmp     eax, 80000000h
0x1800c8d33  jnb     short loc_1800C8D38
0x1800c8d35  mov     r14, rbx
0x1800c8d38  inc     r15d
0x1800c8d3b  lea     rbx, [r13+38h]
0x1800c8d3f  cmp     r15d, [rbx+3Ch]
0x1800c8d43  mov     r8d, 0
0x1800c8d49  jb      short loc_1800C8CF9
0x1800c8d4b  test    r14, r14
0x1800c8d4e  jz      short loc_1800C8D79
0x1800c8d50  mov     edi, [r14+4]
0x1800c8d54  sub     edi, r12d
0x1800c8d57  mov     eax, [rbp+57h+arg_8]
0x1800c8d5a  mov     [r14+10h], eax
0x1800c8d5e  jmp     short loc_1800C8D7C
0x1800c8d60  mov     rsi, rbx
0x1800c8d63  mov     [rbp+57h+var_D0], rbx
0x1800c8d67  lea     rcx, [r13+68h]
0x1800c8d6b  mov     rdx, rbx
0x1800c8d6e  call    sub_180073EF4
0x1800c8d73  lea     rbx, [r13+38h]
0x1800c8d77  jmp     short loc_1800C8D7C
0x1800c8d79  or      edi, 0FFFFFFFFh
0x1800c8d7c  mov     rcx, rbx; lpCriticalSection
0x1800c8d7f  call    cs:LeaveCriticalSection
0x1800c8d85  xor     r12d, r12d
0x1800c8d88  test    rsi, rsi
0x1800c8d8b  jnz     short loc_1800C8DEC
0x1800c8d8d  call    sub_1800C9220
0x1800c8d92  mov     rcx, [rbx+28h]; hHandle
0x1800c8d96  cmp     [rax+158h], r12d
0x1800c8d9d  jz      short loc_1800C8DB4
0x1800c8d9f  mov     [rbp+57h+var_A0], edi
0x1800c8da2  mov     [rbp+57h+var_9C], edi
0x1800c8da5  xor     r8d, r8d
0x1800c8da8  lea     rdx, [rbp+57h+var_A0]
0x1800c8dac  call    cs:Mso20Win32Client_62300
0x1800c8db2  jmp     short loc_1800C8DBC
0x1800c8db4  mov     edx, edi; dwMilliseconds
0x1800c8db6  call    cs:WaitForSingleObject
0x1800c8dbc  cmp     eax, 0FFFFFFFFh
0x1800c8dbf  jnz     short loc_1800C8DD8
0x1800c8dc1  call    sub_1800C9220
0x1800c8dc6  call    cs:GetLastError
0x1800c8dcc  mov     r8d, eax
0x1800c8dcf  lea     rdx, [rbp+57h+var_C8]
0x1800c8dd3  call    sub_1800C87AC
0x1800c8dd8  mov     eax, [rbp+57h+var_C8]
0x1800c8ddb  test    al, 8
0x1800c8ddd  jz      loc_1800C8CCF
0x1800c8de3  mov     rsi, r12
0x1800c8de6  mov     [rbp+57h+var_D0], r12
0x1800c8dea  jmp     short loc_1800C8DEF
0x1800c8dec  mov     eax, [rbp+57h+var_C8]
0x1800c8def  test    al, 8
0x1800c8df1  jz      short loc_1800C8E0C
0x1800c8df3  test    eax, 0FFFFFFFEh
0x1800c8df8  jz      loc_1800C91BC
0x1800c8dfe  lea     rcx, [rbp+57h+var_C8]
0x1800c8e02  call    sub_180098D54
0x1800c8e07  jmp     loc_1800C91BC
0x1800c8e0c  mov     ecx, [rsi]
0x1800c8e0e  test    ecx, ecx
0x1800c8e10  jz      loc_1800C91C1
0x1800c8e16  sub     ecx, 1
0x1800c8e19  jz      loc_1800C9165
0x1800c8e1f  sub     ecx, 1
0x1800c8e22  jz      loc_1800C9146
0x1800c8e28  sub     ecx, 1
0x1800c8e2b  jz      loc_1800C9105
0x1800c8e31  sub     ecx, 1
0x1800c8e34  jz      short loc_1800C8EAA
0x1800c8e36  cmp     ecx, 1
0x1800c8e39  jnz     loc_1800C919C
0x1800c8e3f  mov     rbx, [rsi+8]
0x1800c8e43  mov     [rbx+138h], r12d
0x1800c8e4a  mov     edi, [rbx+134h]
0x1800c8e50  test    edi, edi
0x1800c8e52  jz      short loc_1800C8E9E
0x1800c8e54  call    sub_1800C9220
0x1800c8e59  call    sub_1800C9220
0x1800c8e5e  call    cs:GetTickCount
0x1800c8e64  mov     ecx, edi
0x1800c8e66  sub     ecx, eax
0x1800c8e68  cmp     ecx, 80000000h
0x1800c8e6e  jnb     loc_1800C9146
0x1800c8e74  mov     [rsi+4], edi
0x1800c8e77  call    sub_1800C9220
0x1800c8e7c  lea     r8, [rbp+57h+var_C8]
0x1800c8e80  mov     rdx, rsi
0x1800c8e83  mov     rcx, rax; lpParameter
0x1800c8e86  call    sub_1800C8A60
0x1800c8e8b  test    byte ptr [rbp+57h+var_C8], 8
0x1800c8e8f  jnz     short loc_1800C8E9E
0x1800c8e91  lock inc dword ptr [rbx+170h]
0x1800c8e98  mov     [rbx+138h], edi
0x1800c8e9e  lock dec dword ptr [rbx+170h]
0x1800c8ea5  jmp     loc_1800C919C
0x1800c8eaa  lea     rcx, [r13+118h]; lpCriticalSection
0x1800c8eb1  call    cs:EnterCriticalSection
0x1800c8eb7  mov     ecx, [r13+0F4h]
0x1800c8ebe  mov     eax, 0CCCCCCCDh
0x1800c8ec3  mul     ecx
0x1800c8ec5  mov     edi, edx
0x1800c8ec7  shr     edi, 3
0x1800c8eca  mov     eax, [r13+0F8h]
0x1800c8ed1  cmp     eax, ecx
0x1800c8ed3  jbe     short loc_1800C8ED9
0x1800c8ed5  sub     eax, ecx
0x1800c8ed7  add     edi, eax
0x1800c8ed9  test    edi, edi
0x1800c8edb  jz      loc_1800C90EC
0x1800c8ee1  mov     r15d, r12d
0x1800c8ee4  mov     [rbp+57h+arg_8], r12d
0x1800c8ee8  mov     r14d, r12d
0x1800c8eeb  mov     [rbp+57h+arg_10], r12d
0x1800c8eef  cmp     [r13+114h], r12d
0x1800c8ef6  jbe     loc_1800C90EC
0x1800c8efc  mov     [rbp+57h+var_90], 1
0x1800c8f03  mov     [rbp+57h+var_70], r12d
0x1800c8f07  mov     ecx, r14d
0x1800c8f0a  mov     rax, [r13+108h]
0x1800c8f11  mov     rbx, [rax+rcx*8]
0x1800c8f15  call    sub_1800C9220
0x1800c8f1a  call    cs:GetTickCount
0x1800c8f20  mov     [rsp+110h+var_DC], eax
0x1800c8f24  mov     ecx, [rbx+140h]
0x1800c8f2a  sub     eax, ecx
0x1800c8f2c  shr     eax, 1
0x1800c8f2e  add     eax, ecx
0x1800c8f30  mov     [rsp+110h+var_E0], eax
0x1800c8f34  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800c8f3b  call    cs:EnterCriticalSection
0x1800c8f41  imul    ecx, [rbx+108h], 11h
0x1800c8f48  mov     [rsp+110h+var_D8], ecx
0x1800c8f4c  xor     edx, edx
0x1800c8f4e  mov     [rbp+57h+arg_18], edx
0x1800c8f51  test    ecx, ecx
0x1800c8f53  jz      loc_1800C906A
0x1800c8f59  mov     r13d, [rsp+110h+var_E0]
0x1800c8f5e  mov     esi, [rsp+110h+var_DC]
0x1800c8f62  cmp     r12d, edi
0x1800c8f65  jnb     loc_1800C904D
0x1800c8f6b  mov     edx, [rbx+180h]
0x1800c8f71  inc     edx
0x1800c8f73  mov     [rbx+180h], edx
0x1800c8f79  cmp     edx, ecx
0x1800c8f7b  jb      short loc_1800C8FB1
0x1800c8f7d  call    sub_1800C9220
0x1800c8f82  mov     ecx, [rbx+144h]
0x1800c8f88  mov     eax, esi
0x1800c8f8a  sub     eax, ecx
0x1800c8f8c  cmp     eax, 80000000h
0x1800c8f91  jnb     short loc_1800C8F99
0x1800c8f93  mov     [rbx+140h], ecx
0x1800c8f99  lea     eax, [rsi+5265C00h]
0x1800c8f9f  mov     [rbx+144h], eax
0x1800c8fa5  mov     dword ptr [rbx+180h], 0
0x1800c8faf  xor     edx, edx
0x1800c8fb1  mov     rcx, rbx
0x1800c8fb4  call    sub_180096834
0x1800c8fb9  mov     r14, rax
0x1800c8fbc  xor     edx, edx
0x1800c8fbe  test    rax, rax
0x1800c8fc1  jz      short loc_1800C9039
0x1800c8fc3  cmp     [rax+0D4h], dx
0x1800c8fca  jnz     short loc_1800C9039
0x1800c8fcc  mov     r15d, [rax+0D0h]
0x1800c8fd3  call    sub_1800C9220
0x1800c8fd8  mov     ecx, r13d
0x1800c8fdb  sub     ecx, r15d
0x1800c8fde  cmp     ecx, 80000000h
0x1800c8fe4  jnb     short loc_1800C8FF7
0x1800c8fe6  lea     rdx, [rbp+57h+var_90]
0x1800c8fea  mov     rcx, r14
0x1800c8fed  call    sub_1800BA998
0x1800c8ff2  add     r12d, eax
0x1800c8ff5  jmp     short loc_1800C9031
0x1800c8ff7  mov     eax, [r14+38h]
0x1800c8ffb  and     al, 7
0x1800c8ffd  cmp     al, 2
0x1800c8fff  jbe     short loc_1800C9015
0x1800c9001  movsxd  rax, dword ptr [r14+30h]
0x1800c9005  add     rax, rax
0x1800c9008  mov     ecx, [r14+rax*8+38h]
0x1800c900d  and     cl, 7
0x1800c9010  cmp     cl, 2
0x1800c9013  ja      short loc_1800C9031
0x1800c9015  call    sub_1800C9220
0x1800c901a  mov     eax, [rbx+144h]
0x1800c9020  sub     eax, r15d
0x1800c9023  cmp     eax, 80000000h
0x1800c9028  jnb     short loc_1800C9031
0x1800c902a  mov     [rbx+144h], r15d
0x1800c9031  mov     rcx, r14
0x1800c9034  call    sub_1800BACEC
0x1800c9039  mov     eax, [rbp+57h+arg_18]
0x1800c903c  inc     eax
0x1800c903e  mov     [rbp+57h+arg_18], eax
0x1800c9041  mov     ecx, [rsp+110h+var_D8]
0x1800c9045  cmp     eax, ecx
0x1800c9047  jb      loc_1800C8F62
0x1800c904d  test    r12d, r12d
0x1800c9050  mov     rsi, [rbp+57h+var_D0]
0x1800c9054  mov     r13, [rbp+57h+arg_0]
0x1800c9058  jz      short loc_1800C9062
0x1800c905a  mov     rcx, rbx
0x1800c905d  call    sub_18009674C
0x1800c9062  mov     r15d, [rbp+57h+arg_8]
0x1800c9066  mov     r14d, [rbp+57h+arg_10]
0x1800c906a  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800c9071  call    cs:LeaveCriticalSection
0x1800c9077  add     r15d, r12d
0x1800c907a  mov     [rbp+57h+arg_8], r15d
0x1800c907e  xor     r8d, r8d
0x1800c9081  lea     rdx, [rbp+57h+var_90]
0x1800c9085  mov     rcx, rbx
0x1800c9088  call    sub_180095A14
0x1800c908d  mov     eax, [rbp+57h+var_90]
0x1800c9090  test    al, 8
0x1800c9092  jz      short loc_1800C90A3
0x1800c9094  lea     rdx, [rbp+57h+var_90]
0x1800c9098  mov     rcx, rbx
0x1800c909b  call    sub_180096190
0x1800c90a0  mov     eax, [rbp+57h+var_90]
0x1800c90a3  cmp     r15d, edi
0x1800c90a6  jnb     short loc_1800C90D8
0x1800c90a8  sub     edi, r15d
0x1800c90ab  test    eax, 0FFFFFFFEh
0x1800c90b0  jz      short loc_1800C90BC
0x1800c90b2  lea     rcx, [rbp+57h+var_90]
0x1800c90b6  call    sub_180098D54
0x1800c90bb  nop
0x1800c90bc  inc     r14d
0x1800c90bf  mov     [rbp+57h+arg_10], r14d
0x1800c90c3  cmp     r14d, [r13+114h]
0x1800c90ca  mov     r12d, 0
0x1800c90d0  jb      loc_1800C8EFC
0x1800c90d6  jmp     short loc_1800C90EC
0x1800c90d8  test    eax, 0FFFFFFFEh
0x1800c90dd  jz      short loc_1800C90E9
0x1800c90df  lea     rcx, [rbp+57h+var_90]
0x1800c90e3  call    sub_180098D54
0x1800c90e8  nop
0x1800c90e9  xor     r12d, r12d
0x1800c90ec  mov     [r13+140h], r12d
  ... truncated ...
```
