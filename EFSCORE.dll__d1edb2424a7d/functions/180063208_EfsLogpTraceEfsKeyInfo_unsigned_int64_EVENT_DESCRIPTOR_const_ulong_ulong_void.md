# EfsLogpTraceEfsKeyInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,ulong,ulong,void *)

- ea: `0x180063208`
- end: `0x1800633dc`
- name: `?EfsLogpTraceEfsKeyInfo@@YAX_KPEBU_EVENT_DESCRIPTOR@@KKPEAX@Z`
- size: `468`
- prototype: `void __fastcall(unsigned __int64, const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180063bd4`

## callees

- `0x180062f04`
- `0x180062fac`
- `0x1800630fc`
- `0x180063130`
- `0x18006316c`
- `0x180063208`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063252`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063280`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800632ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063252`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063280`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800632ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006323c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006329e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006336f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063388`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800633a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006323c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006329e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006336f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063388`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800633a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006337d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800633af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006337d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800633af`
- `ntdll!EtwEventWrite` at `0x180063369`
- `ntdll!EtwEventWrite` at `0x180063369`

## pseudocode

```c
void __fastcall EfsLogpTraceEfsKeyInfo(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        char *a5)
{
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  unsigned int v9; // edx
  char *v10; // r14
  char *v11; // rdi
  HANDLE v12; // rax
  char *v13; // rax
  unsigned int v14; // edx
  char *v15; // rsi
  HANDLE v16; // rax
  char *v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  _QWORD v23[4]; // [rsp+20h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+40h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+70h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+80h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+90h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+A0h] [rbp-1h] BYREF

  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0x80u);
  v10 = v8;
  if ( v8 )
  {
    v11 = 0;
    EfsLogpCapabilitiesToString(*((_DWORD *)a5 + 10), v9, v8);
    v12 = GetProcessHeap();
    v13 = (char *)HeapAlloc(v12, 8u, 0x80u);
    v15 = v13;
    if ( v13 )
    {
      EfsLogpKeyTypeToString(*((_DWORD *)a5 + 12), v14, v13);
      v16 = GetProcessHeap();
      v17 = (char *)HeapAlloc(v16, 8u, 0x40u);
      v11 = v17;
      if ( v17 )
      {
        EfsLogpBytesToString(*((_DWORD *)a5 + 1), *((unsigned __int8 **)a5 + 1), v18, v17);
        v23[0] = a5;
        v23[1] = 4;
        v23[2] = a5 + 4;
        v23[3] = 4;
        EfsLogpEventDataDescCreateString(&v24, v11);
        EfsLogpEventDataDescCreateWideString(&v25, *((const unsigned __int16 **)a5 + 2));
        EfsLogpEventDataDescCreateWideString(&v26, *((const unsigned __int16 **)a5 + 3));
        EfsLogpEventDataDescCreateWideString(&v27, *((const unsigned __int16 **)a5 + 4));
        EfsLogpEventDataDescCreateString(&v28, v10);
        EfsLogpEventDataDescCreateString(&v29, v19);
        EfsLogpEventDataDescCreateString(&v30, v15);
        ((void (__fastcall *)(__int64, const struct _EVENT_DESCRIPTOR *, __int64, _QWORD *))EtwEventWrite)(
          a1,
          a2,
          9,
          v23);
      }
    }
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v10);
    if ( v15 )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v15);
    }
    if ( v11 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
  }
}

```

## disassembly

```asm
0x180063208  mov     [rsp-8+arg_10], rbx
0x18006320d  push    rbp
0x18006320e  push    rsi
0x18006320f  push    rdi
0x180063210  push    r12
0x180063212  push    r13
0x180063214  push    r14
0x180063216  push    r15
0x180063218  lea     rbp, [rsp-1Fh]
0x18006321d  sub     rsp, 0C0h
0x180063224  mov     rax, cs:__security_cookie
0x18006322b  xor     rax, rsp
0x18006322e  mov     [rbp+4Fh+var_40], rax
0x180063232  mov     r15, [rbp+4Fh+arg_20]
0x180063236  mov     r13, rdx
0x180063239  mov     r12, rcx
0x18006323c  call    cs:__imp_GetProcessHeap
0x180063242  mov     esi, 80h
0x180063247  mov     rcx, rax; hHeap
0x18006324a  mov     r8d, esi; dwBytes
0x18006324d  lea     ebx, [rsi-78h]
0x180063250  mov     edx, ebx; dwFlags
0x180063252  call    cs:__imp_HeapAlloc
0x180063258  mov     r14, rax
0x18006325b  test    rax, rax
0x18006325e  jz      loc_1800633B5
0x180063264  mov     ecx, [r15+28h]; unsigned int
0x180063268  mov     r8, rax; char *
0x18006326b  xor     edi, edi
0x18006326d  call    ?EfsLogpCapabilitiesToString@@YAXKKPEAD@Z; EfsLogpCapabilitiesToString(ulong,ulong,char *)
0x180063272  call    cs:__imp_GetProcessHeap
0x180063278  mov     r8d, esi; dwBytes
0x18006327b  mov     edx, ebx; dwFlags
0x18006327d  mov     rcx, rax; hHeap
0x180063280  call    cs:__imp_HeapAlloc
0x180063286  mov     rsi, rax
0x180063289  test    rax, rax
0x18006328c  jz      loc_18006336F
0x180063292  mov     ecx, [r15+30h]; unsigned int
0x180063296  mov     r8, rax; char *
0x180063299  call    ?EfsLogpKeyTypeToString@@YAXKKPEAD@Z; EfsLogpKeyTypeToString(ulong,ulong,char *)
0x18006329e  call    cs:__imp_GetProcessHeap
0x1800632a4  lea     r8d, [rbx+38h]; dwBytes
0x1800632a8  mov     edx, ebx; dwFlags
0x1800632aa  mov     rcx, rax; hHeap
0x1800632ad  call    cs:__imp_HeapAlloc
0x1800632b3  mov     rdi, rax
0x1800632b6  test    rax, rax
0x1800632b9  jz      loc_18006336F
0x1800632bf  mov     rdx, [r15+8]; unsigned __int8 *
0x1800632c3  lea     rbx, [r15+4]
0x1800632c7  mov     ecx, [rbx]; unsigned int
0x1800632c9  mov     r9, rax; char *
0x1800632cc  call    ?EfsLogpBytesToString@@YAXKPEAEKPEAD@Z; EfsLogpBytesToString(ulong,uchar *,ulong,char *)
0x1800632d1  cmp     byte ptr [r15+2Ch], 0
0x1800632d6  lea     rax, aFalse; "FALSE"
0x1800632dd  lea     r9, aTrue; "TRUE"
0x1800632e4  mov     [rsp+0F0h+var_D0], r15
0x1800632e9  mov     rdx, rdi; char *
0x1800632ec  mov     [rbp+4Fh+var_C8], 4
0x1800632f4  lea     rcx, [rbp+4Fh+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800632f8  mov     [rbp+4Fh+var_C0], rbx
0x1800632fc  cmovz   r9, rax
0x180063300  mov     [rbp+4Fh+var_B8], 4
0x180063308  call    ?EfsLogpEventDataDescCreateString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBD@Z; EfsLogpEventDataDescCreateString(_EVENT_DATA_DESCRIPTOR *,char const *)
0x18006330d  mov     rdx, [r15+10h]; unsigned __int16 *
0x180063311  lea     rcx, [rbp+4Fh+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x180063315  call    ?EfsLogpEventDataDescCreateWideString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EfsLogpEventDataDescCreateWideString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006331a  mov     rdx, [r15+18h]; unsigned __int16 *
0x18006331e  lea     rcx, [rbp+4Fh+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x180063322  call    ?EfsLogpEventDataDescCreateWideString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EfsLogpEventDataDescCreateWideString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180063327  mov     rdx, [r15+20h]; unsigned __int16 *
0x18006332b  lea     rcx, [rbp+4Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18006332f  call    ?EfsLogpEventDataDescCreateWideString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EfsLogpEventDataDescCreateWideString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180063334  mov     rdx, r14; char *
0x180063337  lea     rcx, [rbp+4Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18006333b  call    ?EfsLogpEventDataDescCreateString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBD@Z; EfsLogpEventDataDescCreateString(_EVENT_DATA_DESCRIPTOR *,char const *)
0x180063340  mov     rdx, r9; char *
0x180063343  lea     rcx, [rbp+4Fh+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x180063347  call    ?EfsLogpEventDataDescCreateString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBD@Z; EfsLogpEventDataDescCreateString(_EVENT_DATA_DESCRIPTOR *,char const *)
0x18006334c  mov     rdx, rsi; char *
0x18006334f  lea     rcx, [rbp+4Fh+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x180063353  call    ?EfsLogpEventDataDescCreateString@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBD@Z; EfsLogpEventDataDescCreateString(_EVENT_DATA_DESCRIPTOR *,char const *)
0x180063358  mov     rdx, r13
0x18006335b  lea     r9, [rsp+0F0h+var_D0]
0x180063360  mov     r8d, 9
0x180063366  mov     rcx, r12
0x180063369  call    cs:__imp_EtwEventWrite
0x18006336f  call    cs:__imp_GetProcessHeap
0x180063375  mov     r8, r14; lpMem
0x180063378  xor     edx, edx; dwFlags
0x18006337a  mov     rcx, rax; hHeap
0x18006337d  call    cs:__imp_HeapFree
0x180063383  test    rsi, rsi
0x180063386  jz      short loc_18006339C
0x180063388  call    cs:__imp_GetProcessHeap
0x18006338e  mov     r8, rsi; lpMem
0x180063391  xor     edx, edx; dwFlags
0x180063393  mov     rcx, rax; hHeap
0x180063396  call    cs:__imp_HeapFree
0x18006339c  test    rdi, rdi
0x18006339f  jz      short loc_1800633B5
0x1800633a1  call    cs:__imp_GetProcessHeap
0x1800633a7  mov     r8, rdi; lpMem
0x1800633aa  xor     edx, edx; dwFlags
0x1800633ac  mov     rcx, rax; hHeap
0x1800633af  call    cs:__imp_HeapFree
0x1800633b5  mov     rcx, [rbp+4Fh+var_40]
0x1800633b9  xor     rcx, rsp; StackCookie
0x1800633bc  call    __security_check_cookie
0x1800633c1  mov     rbx, [rsp+0F0h+arg_10]
0x1800633c9  add     rsp, 0C0h
0x1800633d0  pop     r15
0x1800633d2  pop     r14
0x1800633d4  pop     r13
0x1800633d6  pop     r12
0x1800633d8  pop     rdi
0x1800633d9  pop     rsi
0x1800633da  pop     rbp
0x1800633db  retn
```
