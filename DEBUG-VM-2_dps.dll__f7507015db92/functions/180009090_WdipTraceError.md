# WdipTraceError

- ea: `0x180009090`
- end: `0x180009346`
- name: `WdipTraceError`
- size: `694`
- prototype: `__int64 __fastcall(int, int, int, int, char Args)`
- caller_count: `159`
- callee_count: `4`
- tags: ``

## callers

- `0x180001100`
- `0x180001768`
- `0x180001830`
- `0x180001e88`
- `0x180001ff0`
- `0x180002090`
- `0x180002510`
- `0x180002a08`
- `0x180002dc0`
- `0x180002f10`
- `0x180003020`
- `0x180003498`
- `0x1800035d0`
- `0x180003830`
- `0x180004864`
- `0x180004b18`
- `0x180004c18`
- `0x180004de4`
- `0x1800054f0`
- `0x18000571c`
- `0x1800057b0`
- `0x180005db4`
- `0x180005ec0`
- `0x180006188`
- `0x1800062a8`
- `0x180006360`
- `0x1800064e8`
- `0x1800065b8`
- `0x180006694`
- `0x1800067b8`
- `0x180006834`
- `0x180006c5c`
- `0x180006d08`
- `0x180006e10`
- `0x180006e70`
- `0x180006eec`
- `0x1800071a4`
- `0x180007248`
- `0x1800072cc`
- `0x180007360`
- `0x180007500`
- `0x180007694`
- `0x180007800`
- `0x180007888`
- `0x180007a64`
- `0x180007adc`
- `0x180007d30`
- `0x180007e90`
- `0x180007f80`
- `0x1800080c8`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x18000a864`
- `0x18000f3d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800090fb`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800090fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800092ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800092ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009291`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009291`

## pseudocode

```c
signed int WdipTraceError(__int64 a1, __int64 a2, int a3, const wchar_t *a4, ...)
{
  __int64 v6; // r14
  __int64 v7; // rdi
  bool v8; // zf
  __int64 v9; // rsi
  signed int result; // eax
  unsigned int v11; // esi
  unsigned int v12; // r13d
  __int64 v13; // rax
  WCHAR *v14; // rdi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rsi
  int v17; // eax
  unsigned __int64 v18; // rcx
  WCHAR *v19; // rax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r8
  const wchar_t *v22; // rdx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  unsigned __int64 i; // rbx
  WCHAR *v26; // rcx
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h]
  _BYTE UserData[24]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+58h] [rbp-A8h]
  __int128 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  WCHAR OutputString[1024]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+900h] [rbp+800h] BYREF

  va_start(va, a4);
  v27 = a3;
  memset(UserData, 0, sizeof(UserData));
  v28 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  if ( !EventEnabled(g_hETW, &WDI_DPS_EVENT_DEBUG) )
    return 0;
  v6 = -1;
  v7 = -1;
  do
    v8 = *(_WORD *)(a1 + 2 * v7++ + 2) == 0;
  while ( !v8 );
  v9 = -1;
  do
    v8 = *(_WORD *)(a2 + 2 * v9++ + 2) == 0;
  while ( !v8 );
  result = StringCchPrintfW(OutputString, 0x400u, L"WDI: %s (%s):line-%d :- ", a1, a2, v27);
  if ( result >= 0 )
  {
    v11 = 2 * v9 + 2;
    LODWORD(v28) = v11;
    v12 = 2 * v7 + 2;
    v13 = -1;
    do
      ++v13;
    while ( OutputString[v13] );
    v14 = &OutputString[v13];
    v15 = 1024 - v13;
    if ( 1024 != v13 )
    {
      if ( v15 <= 0x7FFFFFFF )
      {
        v16 = v15 - 1;
        v17 = vsnwprintf(&OutputString[v13], v15 - 1, a4, va);
        if ( v17 < 0 || v17 >= v16 )
          v14[v16] = 0;
        v11 = v28;
        v18 = v15;
        v19 = v14;
        do
        {
          if ( !*v19 )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        v20 = v15 - v18;
        if ( v18 )
        {
          v21 = v15 - v18;
          v22 = L"\n";
          v23 = 2147483646;
          v24 = &v14[v20];
          for ( i = v15 - v21; i; --i )
          {
            if ( !v23 )
              break;
            if ( !*v22 )
              break;
            *v24++ = *v22++;
            --v23;
          }
          v26 = v24 - 1;
          if ( i )
            v26 = v24;
          *v26 = 0;
        }
      }
      else
      {
        *v14 = 0;
      }
    }
    do
      v8 = v14[++v6] == 0;
    while ( !v8 );
    OutputDebugStringW(OutputString);
    *((_QWORD *)&v30 + 1) = &v27;
    *(_QWORD *)UserData = a1;
    v32 = (unsigned int)(2 * v6 + 2);
    *(_QWORD *)&UserData[8] = v12;
    *(_QWORD *)&UserData[16] = a2;
    *(_QWORD *)&v30 = v11;
    *(_QWORD *)&v31 = 4;
    *((_QWORD *)&v31 + 1) = v14;
    return EventWrite(g_hETW, &WDI_DPS_EVENT_DEBUG, 4u, (PEVENT_DATA_DESCRIPTOR)UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180009090  mov     [rsp-8+Format], r9
0x180009095  push    rbp
0x180009096  push    rbx
0x180009097  push    r12
0x180009099  push    r15
0x18000909b  lea     rbp, [rsp-7B8h]
0x1800090a3  sub     rsp, 8B8h
0x1800090aa  mov     rax, cs:__security_cookie
0x1800090b1  xor     rax, rsp
0x1800090b4  mov     [rbp+7D0h+var_50], rax
0x1800090bb  xorps   xmm0, xmm0
0x1800090be  mov     [rsp+8D0h+var_8A0], r8d
0x1800090c3  mov     r15, rcx
0x1800090c6  mov     r12, rdx
0x1800090c9  xor     ecx, ecx
0x1800090cb  lea     rdx, WDI_DPS_EVENT_DEBUG; EventDescriptor
0x1800090d2  mov     ebx, ecx
0x1800090d4  mov     qword ptr [rsp+8D0h+UserData], rcx
0x1800090d9  mov     [rsp+8D0h+var_898], rcx
0x1800090de  xor     eax, eax
0x1800090e0  mov     rcx, cs:g_hETW; RegHandle
0x1800090e7  movups  xmmword ptr [rsp+8D0h+UserData+8], xmm0
0x1800090ec  mov     [rsp+8D0h+var_858], rax
0x1800090f1  movups  [rsp+8D0h+var_878], xmm0
0x1800090f6  movups  [rsp+8D0h+var_868], xmm0
0x1800090fb  call    cs:__imp_EventEnabled
0x180009101  test    al, al
0x180009103  jz      loc_180009342
0x180009109  mov     [rsp+8D0h+var_20], rsi
0x180009111  mov     [rsp+8D0h+var_28], rdi
0x180009119  mov     [rsp+8D0h+var_38], r14
0x180009121  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180009128  mov     rdi, r14
0x18000912b  nop     dword ptr [rax+rax+00h]
0x180009130  cmp     [r15+rdi*2+2], bx
0x180009136  lea     rdi, [rdi+1]
0x18000913a  jnz     short loc_180009130
0x18000913c  mov     rsi, r14
0x18000913f  nop
0x180009140  cmp     [r12+rsi*2+2], bx
0x180009146  lea     rsi, [rsi+1]
0x18000914a  jnz     short loc_180009140
0x18000914c  mov     eax, [rsp+8D0h+var_8A0]
0x180009150  lea     r8, aWdiSSLineD; "WDI: %s (%s):line-%d :- "
0x180009157  mov     [rsp+8D0h+var_8A8], eax
0x18000915b  lea     rcx, [rbp+7D0h+OutputString]; unsigned __int16 *
0x18000915f  mov     ebx, 400h
0x180009164  mov     [rsp+8D0h+var_8B0], r12
0x180009169  mov     edx, ebx; unsigned __int64
0x18000916b  mov     r9, r15
0x18000916e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009173  test    eax, eax
0x180009175  js      loc_18000930D
0x18000917b  lea     esi, ds:2[rsi*2]
0x180009182  mov     [rsp+8D0h+var_30], r13
0x18000918a  mov     dword ptr [rsp+8D0h+var_898], esi
0x18000918e  lea     r13d, ds:2[rdi*2]
0x180009196  lea     rcx, [rbp+7D0h+OutputString]
0x18000919a  mov     rax, r14
0x18000919d  nop     dword ptr [rax]
0x1800091a0  inc     rax
0x1800091a3  cmp     word ptr [rcx+rax*2], 0
0x1800091a8  jnz     short loc_1800091A0
0x1800091aa  lea     rdi, [rbp+7D0h+OutputString]
0x1800091ae  lea     rdi, [rdi+rax*2]
0x1800091b2  sub     rbx, rax
0x1800091b5  jz      loc_180009280
0x1800091bb  cmp     rbx, 7FFFFFFFh
0x1800091c2  jbe     short loc_1800091D7
0x1800091c4  xor     eax, eax
0x1800091c6  mov     [rdi], ax
0x1800091c9  cmp     rbx, 7FFFFFFFh
0x1800091d0  jbe     short loc_18000920B
0x1800091d2  jmp     loc_180009280
0x1800091d7  mov     r8, [rbp+7D0h+Format]; Format
0x1800091de  lea     rsi, [rbx-1]
0x1800091e2  mov     rdx, rsi; BufferCount
0x1800091e5  lea     r9, [rbp+7D0h+Args]; Args
0x1800091ec  mov     rcx, rdi; Buffer
0x1800091ef  call    _vsnwprintf
0x1800091f4  test    eax, eax
0x1800091f6  js      short loc_180009201
0x1800091f8  cdqe
0x1800091fa  cmp     rax, rsi
0x1800091fd  ja      short loc_180009201
0x1800091ff  jnz     short loc_180009207
0x180009201  xor     eax, eax
0x180009203  mov     [rdi+rsi*2], ax
0x180009207  mov     esi, dword ptr [rsp+8D0h+var_898]
0x18000920b  mov     rcx, rbx
0x18000920e  mov     rax, rdi
0x180009211  cmp     word ptr [rax], 0
0x180009215  jz      short loc_180009221
0x180009217  add     rax, 2
0x18000921b  sub     rcx, 1
0x18000921f  jnz     short loc_180009211
0x180009221  xor     r8d, r8d
0x180009224  mov     rax, rbx
0x180009227  sub     rax, rcx
0x18000922a  test    rcx, rcx
0x18000922d  cmovnz  r8, rax
0x180009231  jz      short loc_180009280
0x180009233  lea     rdx, asc_18001DC04; "\n"
0x18000923a  mov     ecx, 7FFFFFFEh
0x18000923f  lea     rax, [rdi+r8*2]
0x180009243  sub     rbx, r8
0x180009246  jz      short loc_18000926C
0x180009248  test    rcx, rcx
0x18000924b  jz      short loc_18000926C
0x18000924d  movzx   r8d, word ptr [rdx]
0x180009251  test    r8w, r8w
0x180009255  jz      short loc_18000926C
0x180009257  mov     [rax], r8w
0x18000925b  add     rdx, 2
0x18000925f  add     rax, 2
0x180009263  dec     rcx
0x180009266  sub     rbx, 1
0x18000926a  jnz     short loc_180009248
0x18000926c  test    rbx, rbx
0x18000926f  lea     rcx, [rax-2]
0x180009273  cmovnz  rcx, rax
0x180009277  xor     eax, eax
0x180009279  mov     [rcx], ax
0x18000927c  nop     dword ptr [rax+00h]
0x180009280  cmp     word ptr [rdi+r14*2+2], 0
0x180009287  lea     r14, [r14+1]
0x18000928b  jnz     short loc_180009280
0x18000928d  lea     rcx, [rbp+7D0h+OutputString]; lpOutputString
0x180009291  call    cs:__imp_OutputDebugStringW
0x180009297  mov     rcx, cs:g_hETW; RegHandle
0x18000929e  lea     rax, [rsp+8D0h+var_8A0]
0x1800092a3  mov     qword ptr [rsp+8D0h+var_878+8], rax
0x1800092a8  lea     r9, [rsp+8D0h+UserData]; UserData
0x1800092ad  lea     eax, ds:2[r14*2]
0x1800092b5  mov     qword ptr [rsp+8D0h+UserData], r15
0x1800092ba  mov     r8d, 4; UserDataCount
0x1800092c0  mov     dword ptr [rsp+8D0h+var_858], eax
0x1800092c4  lea     rdx, WDI_DPS_EVENT_DEBUG; EventDescriptor
0x1800092cb  mov     dword ptr [rsp+8D0h+UserData+8], r13d
0x1800092d0  mov     dword ptr [rsp+8D0h+UserData+0Ch], 0
0x1800092d8  mov     qword ptr [rsp+8D0h+UserData+10h], r12
0x1800092dd  mov     dword ptr [rsp+8D0h+var_878], esi
0x1800092e1  mov     dword ptr [rsp+8D0h+var_878+4], 0
0x1800092e9  mov     qword ptr [rsp+8D0h+var_868], 4
0x1800092f2  mov     qword ptr [rsp+8D0h+var_868+8], rdi
0x1800092f7  mov     dword ptr [rsp+8D0h+var_858+4], 0
0x1800092ff  call    cs:__imp_EventWrite
0x180009305  mov     r13, [rsp+8D0h+var_30]
0x18000930d  mov     rdi, [rsp+8D0h+var_28]
0x180009315  mov     rsi, [rsp+8D0h+var_20]
0x18000931d  mov     r14, [rsp+8D0h+var_38]
0x180009325  mov     rcx, [rbp+7D0h+var_50]
0x18000932c  xor     rcx, rsp; StackCookie
0x18000932f  call    __security_check_cookie
0x180009334  add     rsp, 8B8h
0x18000933b  pop     r15
0x18000933d  pop     r12
0x18000933f  pop     rbx
0x180009340  pop     rbp
0x180009341  retn
0x180009342  mov     eax, ebx
0x180009344  jmp     short loc_180009325
```
