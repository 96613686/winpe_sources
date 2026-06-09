# FaddpReadNextFrameworkFromStream(RtlArray<_FADD_FRAMEWORK> *,RtlMemoryStream *)

- ea: `0x180058350`
- end: `0x18005860b`
- name: `?FaddpReadNextFrameworkFromStream@@YAJPEAV?$RtlArray@U_FADD_FRAMEWORK@@@@PEAVRtlMemoryStream@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(__int64, RtlMemoryStream *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005911c`

## callees

- `0x1800197d4`
- `0x18004ba9c`
- `0x180058350`
- `0x180059920`
- `0x18005a8bc`
- `0x1801182f0`
- `0x180125490`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x180058537`
- `KERNEL32!HeapReAlloc` at `0x180058537`
- `KERNEL32!HeapAlloc` at `0x180058513`
- `KERNEL32!HeapAlloc` at `0x180058513`

## string_xrefs

- `0x1800585d1`: `FaddpReadNextFrameworkFromStream`
- `0x1800585c0`: `RtlMemoryStream failed to read ProgramUsesPrivateCopy [%x]`
- `0x1800583ec`: `RtlMemoryStream failed to read Publisher [%x]`
- `0x1800583c1`: `RtlMemoryStream failed to read Name [%x]`
- `0x180058417`: `RtlMemoryStream failed to read Version [%x]`
- `0x180058442`: `RtlMemoryStream failed to read VersionUsed [%x]`

## pseudocode

```c
__int64 __fastcall FaddpReadNextFrameworkFromStream(__int64 a1, RtlMemoryStream *a2)
{
  int String; // ebx
  unsigned __int64 v5; // r8
  const unsigned __int16 *v6; // r9
  unsigned __int64 v7; // r8
  const unsigned __int16 *v8; // r9
  const char *v9; // r9
  int v10; // r8d
  unsigned __int64 v11; // r8
  const unsigned __int16 *v12; // r9
  unsigned __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // r15
  __int64 v18; // rsi
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // r9
  unsigned __int64 v22; // rsi
  void *v23; // r8
  void *v24; // rcx
  void *v25; // rax
  LPVOID v26; // rbx
  unsigned __int64 v27; // rcx
  void *v28; // rcx
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 Src[260]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33[260]; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int16 v34[260]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v35[260]; // [rsp+658h] [rbp+558h] BYREF
  int v36; // [rsp+860h] [rbp+760h]

  if ( *((_QWORD *)a2 + 4) < *((_QWORD *)a2 + 1) )
  {
    memset_0(Src, 0, 0x824u);
    String = RtlMemoryStream::ReadString(a2, Src, v5, v6);
    if ( String < 0 )
    {
      v9 = "RtlMemoryStream failed to read Name [%x]";
      v10 = 2181;
LABEL_34:
      AslLogCallPrintf(1, (unsigned int)"FaddpReadNextFrameworkFromStream", v10, (_DWORD)v9);
      return (unsigned int)String;
    }
    String = RtlMemoryStream::ReadString(a2, v33, v7, v8);
    if ( String < 0 )
    {
      v9 = "RtlMemoryStream failed to read Publisher [%x]";
      v10 = 2187;
      goto LABEL_34;
    }
    String = RtlMemoryStream::ReadString(a2, v34, v11, v12);
    if ( String < 0 )
    {
      v9 = "RtlMemoryStream failed to read Version [%x]";
      v10 = 2193;
      goto LABEL_34;
    }
    String = RtlMemoryStream::ReadString(a2, v35, v13, v14);
    if ( String < 0 )
    {
      v9 = "RtlMemoryStream failed to read VersionUsed [%x]";
      v10 = 2199;
      goto LABEL_34;
    }
    v15 = *((_QWORD *)a2 + 4);
    if ( v15 > *((_QWORD *)a2 + 1) || (v16 = v15 + 4, v15 + 4 < v15) || v16 > *((_QWORD *)a2 + 1) )
    {
      String = -2147024809;
      v9 = "RtlMemoryStream failed to read ProgramUsesPrivateCopy [%x]";
      v10 = 2205;
      goto LABEL_34;
    }
    v36 = *(_DWORD *)(v15 + *((_QWORD *)a2 + 5));
    *((_QWORD *)a2 + 4) = v16;
    v17 = *(_QWORD *)(a1 + 16);
    if ( v17 >= *(_QWORD *)(a1 + 24) )
    {
      if ( v17 + 1 <= *(_QWORD *)(a1 + 24) )
      {
        String = -2147024809;
LABEL_32:
        v9 = "Failed to append framework from stream [%x]";
        v10 = 2211;
        goto LABEL_34;
      }
      v18 = *(_QWORD *)(a1 + 32) - 1LL;
      if ( *(_QWORD *)(a1 + 32) + v17 < v17 + 1
        || (v19 = *(_QWORD *)(a1 + 8), v20 = *(_QWORD *)(a1 + 24), dwBytes = 0, (int)ULongLongMult(v20, v19, &v31) < 0)
        || (v22 = v21 & ~v18, (int)ULongLongMult(v22, *(_QWORD *)(a1 + 8), &dwBytes) < 0) )
      {
        String = -2147483637;
        goto LABEL_32;
      }
      v23 = *(void **)(a1 + 40);
      v24 = *(void **)a1;
      if ( v23 )
      {
        v26 = HeapReAlloc(v24, 0, v23, dwBytes);
      }
      else
      {
        v25 = HeapAlloc(v24, 0, dwBytes);
        v26 = v25;
        if ( v25 )
          memset_0(v25, 0, dwBytes);
      }
      if ( !v26 )
      {
        String = -2147024882;
        goto LABEL_32;
      }
      *(_QWORD *)(a1 + 40) = v26;
      *(_QWORD *)(a1 + 24) = v22;
    }
    v27 = *(_QWORD *)(a1 + 8);
    dwBytes = 0;
    if ( (int)ULongLongMult(v27, v17, &dwBytes) >= 0 )
    {
      v28 = (void *)(*(_QWORD *)(a1 + 40) + dwBytes);
      if ( (unsigned __int64)v28 >= *(_QWORD *)(a1 + 40) )
      {
        memcpy_0(v28, Src, 0x824u);
        ++*(_QWORD *)(a1 + 16);
        return 0;
      }
    }
    String = -2147483637;
    goto LABEL_32;
  }
  return (unsigned int)-2147024637;
}

```

## disassembly

```asm
0x180058350  mov     [rsp-8+arg_10], rbx
0x180058355  mov     [rsp-8+arg_18], rsi
0x18005835a  push    rbp
0x18005835b  push    rdi
0x18005835c  push    r15
0x18005835e  lea     rbp, [rsp-780h]
0x180058366  sub     rsp, 880h
0x18005836d  mov     rax, cs:__security_cookie
0x180058374  xor     rax, rsp
0x180058377  mov     [rbp+790h+var_20], rax
0x18005837e  mov     rax, [rdx+8]
0x180058382  mov     rsi, rdx
0x180058385  mov     rdi, rcx
0x180058388  cmp     [rdx+20h], rax
0x18005838c  jb      short loc_180058398
0x18005838e  mov     ebx, 80070103h
0x180058393  jmp     loc_1800585E2
0x180058398  xor     edx, edx; Val
0x18005839a  lea     rcx, [rsp+890h+Src]; void *
0x18005839f  mov     r8d, 824h; Size
0x1800583a5  call    memset_0
0x1800583aa  lea     rdx, [rsp+890h+Src]; unsigned __int16 *
0x1800583af  mov     rcx, rsi; this
0x1800583b2  call    ?ReadString@RtlMemoryStream@@QEAAJPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x1800583b7  mov     ebx, eax
0x1800583b9  test    eax, eax
0x1800583bb  jns     short loc_1800583D3
0x1800583bd  mov     [rsp+890h+var_870], eax
0x1800583c1  lea     r9, aRtlmemorystrea_1; "RtlMemoryStream failed to read Name [%x"...
0x1800583c8  mov     r8d, 885h
0x1800583ce  jmp     loc_1800585D1
0x1800583d3  lea     rdx, [rbp+790h+var_648]; unsigned __int16 *
0x1800583da  mov     rcx, rsi; this
0x1800583dd  call    ?ReadString@RtlMemoryStream@@QEAAJPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x1800583e2  mov     ebx, eax
0x1800583e4  test    eax, eax
0x1800583e6  jns     short loc_1800583FE
0x1800583e8  mov     [rsp+890h+var_870], eax
0x1800583ec  lea     r9, aRtlmemorystrea_3; "RtlMemoryStream failed to read Publishe"...
0x1800583f3  mov     r8d, 88Bh
0x1800583f9  jmp     loc_1800585D1
0x1800583fe  lea     rdx, [rbp+790h+var_440]; unsigned __int16 *
0x180058405  mov     rcx, rsi; this
0x180058408  call    ?ReadString@RtlMemoryStream@@QEAAJPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x18005840d  mov     ebx, eax
0x18005840f  test    eax, eax
0x180058411  jns     short loc_180058429
0x180058413  mov     [rsp+890h+var_870], eax
0x180058417  lea     r9, aRtlmemorystrea_9; "RtlMemoryStream failed to read Version "...
0x18005841e  mov     r8d, 891h
0x180058424  jmp     loc_1800585D1
0x180058429  lea     rdx, [rbp+790h+var_238]; unsigned __int16 *
0x180058430  mov     rcx, rsi; this
0x180058433  call    ?ReadString@RtlMemoryStream@@QEAAJPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x180058438  mov     ebx, eax
0x18005843a  test    eax, eax
0x18005843c  jns     short loc_180058454
0x18005843e  mov     [rsp+890h+var_870], eax
0x180058442  lea     r9, aRtlmemorystrea_6; "RtlMemoryStream failed to read VersionU"...
0x180058449  mov     r8d, 897h
0x18005844f  jmp     loc_1800585D1
0x180058454  mov     rcx, [rsi+20h]
0x180058458  cmp     rcx, [rsi+8]
0x18005845c  ja      loc_1800585BB
0x180058462  lea     rdx, [rcx+4]
0x180058466  cmp     rdx, rcx
0x180058469  jb      loc_1800585BB
0x18005846f  cmp     rdx, [rsi+8]
0x180058473  ja      loc_1800585BB
0x180058479  mov     rax, [rsi+28h]
0x18005847d  mov     ecx, [rcx+rax]
0x180058480  mov     [rbp+790h+var_30], ecx
0x180058486  mov     [rsi+20h], rdx
0x18005848a  mov     r15, [rdi+10h]
0x18005848e  cmp     r15, [rdi+18h]
0x180058492  jb      loc_18005855C
0x180058498  lea     rcx, [r15+1]
0x18005849c  cmp     rcx, [rdi+18h]
0x1800584a0  ja      short loc_1800584AC
0x1800584a2  mov     ebx, 80070057h
0x1800584a7  jmp     loc_18005854A
0x1800584ac  mov     rsi, [rdi+20h]
0x1800584b0  dec     rsi
0x1800584b3  lea     r9, [rsi+rcx]
0x1800584b7  cmp     r9, rcx
0x1800584ba  jnb     short loc_1800584C6
0x1800584bc  mov     ebx, 8000000Bh
0x1800584c1  jmp     loc_18005854A
0x1800584c6  mov     rdx, [rdi+8]; unsigned __int64
0x1800584ca  lea     r8, [rsp+890h+var_858]; unsigned __int64 *
0x1800584cf  mov     rcx, [rdi+18h]; unsigned __int64
0x1800584d3  mov     [rsp+890h+dwBytes], 0
0x1800584dc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800584e1  test    eax, eax
0x1800584e3  js      short loc_1800584BC
0x1800584e5  mov     rdx, [rdi+8]; unsigned __int64
0x1800584e9  lea     r8, [rsp+890h+dwBytes]; unsigned __int64 *
0x1800584ee  not     rsi
0x1800584f1  and     rsi, r9
0x1800584f4  mov     rcx, rsi; unsigned __int64
0x1800584f7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800584fc  test    eax, eax
0x1800584fe  js      short loc_1800584BC
0x180058500  mov     r8, [rdi+28h]; lpMem
0x180058504  xor     edx, edx; dwFlags
0x180058506  mov     rcx, [rdi]; hHeap
0x180058509  test    r8, r8
0x18005850c  jnz     short loc_180058532
0x18005850e  mov     r8, [rsp+890h+dwBytes]; dwBytes
0x180058513  call    cs:__imp_HeapAlloc
0x180058519  mov     rbx, rax
0x18005851c  test    rax, rax
0x18005851f  jz      short loc_180058540
0x180058521  mov     r8, [rsp+890h+dwBytes]; Size
0x180058526  xor     edx, edx; Val
0x180058528  mov     rcx, rax; void *
0x18005852b  call    memset_0
0x180058530  jmp     short loc_180058540
0x180058532  mov     r9, [rsp+890h+dwBytes]; dwBytes
0x180058537  call    cs:__imp_HeapReAlloc
0x18005853d  mov     rbx, rax
0x180058540  test    rbx, rbx
0x180058543  jnz     short loc_180058554
0x180058545  mov     ebx, 8007000Eh
0x18005854a  test    ebx, ebx
0x18005854c  jns     loc_1800585E2
0x180058552  jmp     short loc_1800585A6
0x180058554  mov     [rdi+28h], rbx
0x180058558  mov     [rdi+18h], rsi
0x18005855c  mov     rcx, [rdi+8]; unsigned __int64
0x180058560  lea     r8, [rsp+890h+dwBytes]; unsigned __int64 *
0x180058565  mov     rdx, r15; unsigned __int64
0x180058568  mov     [rsp+890h+dwBytes], 0
0x180058571  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180058576  test    eax, eax
0x180058578  js      short loc_1800585A1
0x18005857a  mov     rcx, [rsp+890h+dwBytes]
0x18005857f  add     rcx, [rdi+28h]; void *
0x180058583  cmp     rcx, [rdi+28h]
0x180058587  jb      short loc_1800585A1
0x180058589  lea     rdx, [rsp+890h+Src]; Src
0x18005858e  mov     r8d, 824h; Size
0x180058594  call    memcpy_0
0x180058599  inc     qword ptr [rdi+10h]
0x18005859d  xor     ebx, ebx
0x18005859f  jmp     short loc_1800585E2
0x1800585a1  mov     ebx, 8000000Bh
0x1800585a6  mov     eax, ebx
0x1800585a8  mov     [rsp+890h+var_870], ebx
0x1800585ac  lea     r9, aFailedToAppend; "Failed to append framework from stream "...
0x1800585b3  mov     r8d, 8A3h
0x1800585b9  jmp     short loc_1800585D1
0x1800585bb  mov     ebx, 80070057h
0x1800585c0  lea     r9, aRtlmemorystrea_8; "RtlMemoryStream failed to read ProgramU"...
0x1800585c7  mov     [rsp+890h+var_870], ebx
0x1800585cb  mov     r8d, 89Dh
0x1800585d1  lea     rdx, aFaddpreadnextf_0; "FaddpReadNextFrameworkFromStream"
0x1800585d8  mov     ecx, 1
0x1800585dd  call    AslLogCallPrintf
0x1800585e2  mov     eax, ebx
0x1800585e4  mov     rcx, [rbp+790h+var_20]
0x1800585eb  xor     rcx, rsp; StackCookie
0x1800585ee  call    __security_check_cookie
0x1800585f3  lea     r11, [rsp+890h+var_10]
0x1800585fb  mov     rbx, [r11+30h]
0x1800585ff  mov     rsi, [r11+38h]
0x180058603  mov     rsp, r11
0x180058606  pop     r15
0x180058608  pop     rdi
0x180058609  pop     rbp
0x18005860a  retn
```
