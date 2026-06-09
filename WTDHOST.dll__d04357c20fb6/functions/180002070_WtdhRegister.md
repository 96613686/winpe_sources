# WtdhRegister

- ea: `0x180002070`
- end: `0x180002257`
- name: `WtdhRegister`
- size: `487`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000108c`
- `0x180001550`
- `0x180002070`
- `0x180002928`
- `0x180002ddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000209e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000209e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002114`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000212c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002114`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000212c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000221b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000221b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000213a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000213a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002237`

## pseudocode

```c
__int64 WtdhRegister()
{
  HANDLE v0; // rdi
  HANDLE EventW; // rsi
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int LastError; // ebx
  HANDLE v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  HANDLE hObject; // [rsp+30h] [rbp-29h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-19h] BYREF
  HANDLE *p_hObject; // [rsp+60h] [rbp+7h]
  __int64 v13; // [rsp+68h] [rbp+Fh]
  __int64 *v14; // [rsp+70h] [rbp+17h]
  __int64 v15; // [rsp+78h] [rbp+1Fh]

  v0 = 0;
  hObject = 0;
  EventW = 0;
  EnterCriticalSection(&CriticalSection);
  if ( hDevice )
  {
    LastError = 183;
LABEL_19:
    if ( (unsigned int)dword_180007000 > 2
      && (qword_180007010 & 0x400000000000LL) != 0
      && (*(_QWORD *)&qword_180007018 & 0x400000000000LL) == *(_QWORD *)&qword_180007018 )
    {
      LODWORD(hObject) = LastError;
      p_hObject = &hObject;
      v13 = 4;
      v14 = &v10;
      v10 = 0x1000000;
      v15 = 8;
      sub_18000108C(*(__int64 *)&qword_180007018, (unsigned __int8 *)&word_18000584A, v2, v3, 4u, &v11);
    }
    goto LABEL_23;
  }
  if ( byte_180007158 )
  {
    LastError = 87;
    goto LABEL_19;
  }
  if ( hEvent )
    sub_180002DDC();
  if ( byte_180007170 )
    sub_180002DDC();
  if ( Overlapped.hEvent )
    sub_180002DDC();
  LastError = sub_180002928(&hObject);
  if ( LastError )
  {
    v0 = hObject;
    goto LABEL_19;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW || (v5 = CreateEventW(0, 1, 0, 0)) == 0 )
  {
    LastError = GetLastError();
    v0 = hObject;
    if ( !LastError )
      goto LABEL_23;
    goto LABEL_19;
  }
  v0 = 0;
  Overlapped.hEvent = EventW;
  EventW = 0;
  hDevice = hObject;
  hEvent = v5;
  if ( (unsigned int)dword_180007000 > 4 )
    sub_18000108C((__int64)v5, (unsigned __int8 *)byte_1800056F9, v6, v7, 2u, &v11);
LABEL_23:
  LeaveCriticalSection(&CriticalSection);
  if ( EventW )
    CloseHandle(EventW);
  if ( v0 )
    CloseHandle(v0);
  return LastError;
}

```

## disassembly

```asm
0x180002070  push    rbp
0x180002072  push    rbx
0x180002073  push    rsi
0x180002074  push    rdi
0x180002075  lea     rbp, [rsp-3Fh]
0x18000207a  sub     rsp, 98h
0x180002081  mov     rax, cs:__security_cookie
0x180002088  xor     rax, rsp
0x18000208b  mov     [rbp+57h+var_30], rax
0x18000208f  xor     edi, edi
0x180002091  lea     rcx, CriticalSection; lpCriticalSection
0x180002098  mov     [rbp+57h+hObject], rdi
0x18000209c  xor     esi, esi
0x18000209e  call    cs:EnterCriticalSection
0x1800020a4  cmp     cs:hDevice, rsi
0x1800020ab  jz      short loc_1800020B7
0x1800020ad  mov     ebx, 0B7h
0x1800020b2  jmp     loc_180002199
0x1800020b7  cmp     cs:byte_180007158, sil
0x1800020be  jz      short loc_1800020CA
0x1800020c0  mov     ebx, 57h ; 'W'
0x1800020c5  jmp     loc_180002199
0x1800020ca  cmp     cs:hEvent, rsi
0x1800020d1  jz      short loc_1800020D8
0x1800020d3  call    sub_180002DDC
0x1800020d8  cmp     cs:byte_180007170, sil
0x1800020df  jz      short loc_1800020E6
0x1800020e1  call    sub_180002DDC
0x1800020e6  cmp     cs:Overlapped.hEvent, rsi
0x1800020ed  jz      short loc_1800020F4
0x1800020ef  call    sub_180002DDC
0x1800020f4  lea     rcx, [rbp+57h+hObject]
0x1800020f8  call    sub_180002928
0x1800020fd  mov     ebx, eax
0x1800020ff  test    eax, eax
0x180002101  jnz     loc_180002195
0x180002107  lea     edi, [rax+1]
0x18000210a  xor     r9d, r9d; lpName
0x18000210d  mov     edx, edi; bManualReset
0x18000210f  xor     r8d, r8d; bInitialState
0x180002112  xor     ecx, ecx; lpEventAttributes
0x180002114  call    cs:CreateEventW
0x18000211a  mov     rsi, rax
0x18000211d  test    rax, rax
0x180002120  jz      short loc_18000213A
0x180002122  xor     r9d, r9d; lpName
0x180002125  xor     r8d, r8d; bInitialState
0x180002128  mov     edx, edi; bManualReset
0x18000212a  xor     ecx, ecx; lpEventAttributes
0x18000212c  call    cs:CreateEventW
0x180002132  mov     rcx, rax
0x180002135  test    rax, rax
0x180002138  jnz     short loc_18000214F
0x18000213a  call    cs:GetLastError
0x180002140  mov     ebx, eax
0x180002142  mov     rdi, [rbp+57h+hObject]
0x180002146  test    eax, eax
0x180002148  jnz     short loc_180002199
0x18000214a  jmp     loc_180002214
0x18000214f  mov     rax, [rbp+57h+hObject]
0x180002153  xor     edi, edi
0x180002155  mov     cs:Overlapped.hEvent, rsi
0x18000215c  xor     esi, esi
0x18000215e  mov     cs:hDevice, rax
0x180002165  mov     eax, cs:dword_180007000
0x18000216b  mov     cs:hEvent, rcx
0x180002172  cmp     eax, 4
0x180002175  jbe     loc_180002214
0x18000217b  lea     rax, [rbp+57h+var_70]
0x18000217f  mov     [rsp+0B0h+var_88], rax
0x180002184  lea     rdx, byte_1800056F9
0x18000218b  mov     [rsp+0B0h+var_90], 2
0x180002193  jmp     short loc_18000220F
0x180002195  mov     rdi, [rbp+57h+hObject]
0x180002199  mov     eax, cs:dword_180007000
0x18000219f  cmp     eax, 2
0x1800021a2  jbe     short loc_180002214
0x1800021a4  mov     rcx, cs:qword_180007018; int
0x1800021ab  mov     rdx, 400000000000h
0x1800021b5  mov     rax, cs:qword_180007010
0x1800021bc  test    rdx, rax
0x1800021bf  jz      short loc_180002214
0x1800021c1  mov     rax, rcx
0x1800021c4  and     rax, rdx
0x1800021c7  cmp     rax, rcx
0x1800021ca  jnz     short loc_180002214
0x1800021cc  lea     rax, [rbp+57h+hObject]
0x1800021d0  mov     dword ptr [rbp+57h+hObject], ebx
0x1800021d3  mov     [rbp+57h+var_50], rax
0x1800021d7  lea     rdx, word_18000584A; int
0x1800021de  lea     rax, [rbp+57h+var_78]
0x1800021e2  mov     [rbp+57h+var_48], 4
0x1800021ea  mov     [rbp+57h+var_40], rax
0x1800021ee  lea     rax, [rbp+57h+var_70]
0x1800021f2  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x1800021f7  mov     [rsp+0B0h+var_90], 4; ULONG
0x1800021ff  mov     [rbp+57h+var_78], 1000000h
0x180002207  mov     [rbp+57h+var_38], 8
0x18000220f  call    sub_18000108C
0x180002214  lea     rcx, CriticalSection; lpCriticalSection
0x18000221b  call    cs:LeaveCriticalSection
0x180002221  test    rsi, rsi
0x180002224  jz      short loc_18000222F
0x180002226  mov     rcx, rsi; hObject
0x180002229  call    cs:CloseHandle
0x18000222f  test    rdi, rdi
0x180002232  jz      short loc_18000223D
0x180002234  mov     rcx, rdi; hObject
0x180002237  call    cs:CloseHandle
0x18000223d  mov     eax, ebx
0x18000223f  mov     rcx, [rbp+57h+var_30]
0x180002243  xor     rcx, rsp; StackCookie
0x180002246  call    __security_check_cookie
0x18000224b  add     rsp, 98h
0x180002252  pop     rdi
0x180002253  pop     rsi
0x180002254  pop     rbx
0x180002255  pop     rbp
0x180002256  retn
```
