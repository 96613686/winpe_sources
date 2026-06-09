# UndetectedInstallerParseLuafvEvent(uint *,int *,void * *,ushort * *,ushort * *,RtlMemoryStream &)

- ea: `0x180050394`
- end: `0x180050957`
- name: `?UndetectedInstallerParseLuafvEvent@@YAKPEAIPEAHPEAPEAXPEAPEAG3AEAVRtlMemoryStream@@@Z`
- size: `1475`
- prototype: `unsigned int __fastcall(unsigned int *, int *, void **, unsigned __int16 **, unsigned __int16 **, struct RtlMemoryStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800b6cfc`

## callees

- `0x180012920`
- `0x180050394`
- `0x180056256`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180050896`
- `ntdll!RtlFreeHeap` at `0x1800508b3`
- `ntdll!RtlFreeHeap` at `0x1800508d4`
- `ntdll!RtlFreeHeap` at `0x180050896`
- `ntdll!RtlFreeHeap` at `0x1800508b3`
- `ntdll!RtlFreeHeap` at `0x1800508d4`
- `ntdll!RtlAllocateHeap` at `0x18005044f`
- `ntdll!RtlAllocateHeap` at `0x18005059e`
- `ntdll!RtlAllocateHeap` at `0x1800506d2`
- `ntdll!RtlAllocateHeap` at `0x18005044f`
- `ntdll!RtlAllocateHeap` at `0x18005059e`
- `ntdll!RtlAllocateHeap` at `0x1800506d2`
- `ntdll!RtlValidSid` at `0x1800504d1`
- `ntdll!RtlValidSid` at `0x1800504d1`

## string_xrefs

- `0x180050421`: `UndetectedInstallerParseLuafvEvent`
- `0x18005046a`: `UndetectedInstallerParseLuafvEvent`
- `0x1800504ed`: `UndetectedInstallerParseLuafvEvent`
- `0x180050562`: `UndetectedInstallerParseLuafvEvent`
- `0x1800505b9`: `UndetectedInstallerParseLuafvEvent`
- `0x180050872`: `UndetectedInstallerParseLuafvEvent`
- `0x1800508e8`: `UndetectedInstallerParseLuafvEvent`
- `0x180050936`: `UndetectedInstallerParseLuafvEvent`
- `0x180050686`: `Error reading exclusions from event stream [%d]`
- `0x180050846`: `Error reading exclusions from event stream [%d]`
- `0x1800508e1`: `Error reading exclusions from event stream [%d]`
- `0x180050860`: `Error reading user sid [%d]`
- `0x1800507eb`: `Error reading desired access from event stream [%d]`
- `0x18005045d`: `Error allocating user sid.`
- `0x180050414`: `Invalid user sid length`
- `0x1800504db`: `Invalid user sid.`

## pseudocode

```c
__int64 __fastcall UndetectedInstallerParseLuafvEvent(
        unsigned int *a1,
        int *a2,
        void **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        struct RtlMemoryStream *a6)
{
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r10
  __int64 v9; // r9
  unsigned int v10; // ebx
  SIZE_T v11; // rax
  size_t v12; // rdi
  PVOID Heap; // r13
  size_t v14; // rcx
  char *v15; // r12
  char *v16; // r15
  int v17; // eax
  size_t v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rbp
  int v22; // r8d
  unsigned int v23; // ecx
  __int64 v24; // r14
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rbp
  unsigned __int64 v28; // rcx
  __int64 v29; // rbp
  int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // ecx
  __int64 v33; // rbx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  int v38; // ecx
  unsigned int v44; // [rsp+A8h] [rbp+30h]

  v7 = *((_QWORD *)a6 + 1);
  v8 = v7 - 4;
  if ( v7 < 4 )
  {
    v10 = 160;
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerParseLuafvEvent",
      192,
      (unsigned int)"Error setting stream position to %d [%d]",
      v8,
      160);
    return v10;
  }
  *((_QWORD *)a6 + 4) = v8;
  v9 = *((_QWORD *)a6 + 5);
  v44 = *(_DWORD *)(v9 + v8);
  *((_QWORD *)a6 + 4) = v7;
  v10 = 8;
  *((_QWORD *)a6 + 4) = 4;
  if ( v7 < 8 )
  {
    v10 = 160;
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerParseLuafvEvent",
      217,
      (unsigned int)"Error reading exclusions from event stream [%d]",
      160);
    return v10;
  }
  v11 = *(unsigned int *)(v9 + 4);
  *((_QWORD *)a6 + 4) = 8;
  if ( !(_DWORD)v11 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerParseLuafvEvent",
      222,
      (unsigned int)"Invalid user sid length");
    return 1359;
  }
  v12 = v11;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
  if ( !Heap )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerParseLuafvEvent",
      233,
      (unsigned int)"Error allocating user sid.");
    return v10;
  }
  v14 = *((_QWORD *)a6 + 4);
  v15 = 0;
  v16 = 0;
  if ( v14 > *((_QWORD *)a6 + 1) || v14 + v12 < v14 || v14 + v12 > *((_QWORD *)a6 + 1) )
  {
    v17 = 160;
LABEL_67:
    v31 = "Error reading user sid [%d]";
    v30 = 240;
    goto LABEL_68;
  }
  memcpy_0(Heap, (const void *)(v14 + *((_QWORD *)a6 + 5)), v12);
  v18 = *((_QWORD *)a6 + 4);
  if ( v18 + v12 < v18 )
  {
    *((_QWORD *)a6 + 4) = -1;
    v17 = 534;
    goto LABEL_67;
  }
  *((_QWORD *)a6 + 4) = v18 + v12;
  if ( RtlValidSid(Heap) )
  {
    v19 = *((_QWORD *)a6 + 4);
    if ( v19 > *((_QWORD *)a6 + 1) || (v20 = v19 + 2, v19 + 2 < v19) || v20 > *((_QWORD *)a6 + 1) )
    {
      v17 = 160;
      v31 = "Error reading exclusions from event stream [%d]";
      v30 = 257;
      goto LABEL_68;
    }
    v21 = *(unsigned __int16 *)(v19 + *((_QWORD *)a6 + 5));
    *((_QWORD *)a6 + 4) = v20;
    if ( !(_WORD)v21 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"UndetectedInstallerParseLuafvEvent",
        262,
        (unsigned int)"Invalid file name length");
      goto LABEL_14;
    }
    if ( (unsigned __int16)(v21 + 1) < (unsigned __int16)v21 )
    {
      v22 = 272;
LABEL_22:
      AslLogCallPrintf(
        1,
        (unsigned int)"UndetectedInstallerParseLuafvEvent",
        v22,
        (unsigned int)"Integer overflow calculating filename length.");
LABEL_23:
      v10 = 534;
      goto LABEL_69;
    }
    v23 = 2 * (unsigned __int16)(v21 + 1);
    if ( v23 > 0xFFFF )
    {
      v22 = 278;
      goto LABEL_22;
    }
    v15 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)v23);
    if ( !v15 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"UndetectedInstallerParseLuafvEvent",
        285,
        (unsigned int)"Error allocating file name buffer.");
      goto LABEL_69;
    }
    v24 = 2 * v21;
    if ( !(2 * v21) )
      goto LABEL_34;
    v25 = *((_QWORD *)a6 + 4);
    if ( v25 > *((_QWORD *)a6 + 1) || v25 + v24 < v25 || v25 + v24 > *((_QWORD *)a6 + 1) )
    {
      v17 = 160;
    }
    else
    {
      memcpy_0(v15, (const void *)(v25 + *((_QWORD *)a6 + 5)), 2 * v21);
      v26 = *((_QWORD *)a6 + 4);
      if ( v26 + v24 >= v26 )
      {
        *((_QWORD *)a6 + 4) = v26 + v24;
LABEL_34:
        *(_WORD *)&v15[v24] = 0;
        v27 = *((_QWORD *)a6 + 4);
        if ( v27 > *((_QWORD *)a6 + 1) || (v28 = v27 + 2, v27 + 2 < v27) || v28 > *((_QWORD *)a6 + 1) )
        {
          v17 = 160;
          v30 = 305;
        }
        else
        {
          v29 = *(unsigned __int16 *)(*((_QWORD *)a6 + 5) + v27);
          *((_QWORD *)a6 + 4) = v28;
          if ( !(_WORD)v29 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"UndetectedInstallerParseLuafvEvent",
              310,
              (unsigned int)"Invalid file name length");
            goto LABEL_14;
          }
          if ( (unsigned __int16)(v29 + 1) < (unsigned __int16)v29 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"UndetectedInstallerParseLuafvEvent",
              320,
              (unsigned int)"Integer overflow calculating imagename length.");
            goto LABEL_23;
          }
          v32 = 2 * (unsigned __int16)(v29 + 1);
          if ( v32 > 0xFFFF )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"UndetectedInstallerParseLuafvEvent",
              326,
              (unsigned int)"Integer overflow calculating imagename length.");
            goto LABEL_23;
          }
          v16 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)v32);
          if ( !v16 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"UndetectedInstallerParseLuafvEvent",
              333,
              (unsigned int)"Error allocating image name buffer.");
            goto LABEL_69;
          }
          v33 = 2 * v29;
          if ( !(2 * v29) )
            goto LABEL_54;
          v34 = *((_QWORD *)a6 + 4);
          if ( v34 > *((_QWORD *)a6 + 1) || v33 + v34 < v34 || v33 + v34 > *((_QWORD *)a6 + 1) )
          {
            v17 = 160;
          }
          else
          {
            memcpy_0(v16, (const void *)(v34 + *((_QWORD *)a6 + 5)), 2 * v29);
            v35 = *((_QWORD *)a6 + 4);
            if ( v35 + v33 >= v35 )
            {
              *((_QWORD *)a6 + 4) = v35 + v33;
LABEL_54:
              *(_WORD *)&v16[v33] = 0;
              v36 = *((_QWORD *)a6 + 4) + 4LL;
              if ( v36 > *((_QWORD *)a6 + 1) )
              {
                v17 = 160;
                v31 = "Error setting stream position [%d]";
                v30 = 352;
              }
              else
              {
                v37 = *((_QWORD *)a6 + 4) + 8LL;
                *((_QWORD *)a6 + 4) = v36;
                if ( v36 + 4 >= v36 && v37 <= *((_QWORD *)a6 + 1) )
                {
                  v38 = *(_DWORD *)(v36 + *((_QWORD *)a6 + 5));
                  *((_QWORD *)a6 + 4) = v37;
                  v10 = 0;
                  *a1 = v44;
                  *a2 = (v38 & 0xD0156) != 0;
                  *a3 = Heap;
                  *a4 = (unsigned __int16 *)v15;
                  *a5 = (unsigned __int16 *)v16;
                  return v10;
                }
                v17 = 160;
                v31 = "Error reading desired access from event stream [%d]";
                v30 = 358;
              }
              goto LABEL_68;
            }
            *((_QWORD *)a6 + 4) = -1;
            v17 = 534;
          }
          v30 = 340;
        }
        goto LABEL_41;
      }
      *((_QWORD *)a6 + 4) = -1;
      v17 = 534;
    }
    v30 = 292;
LABEL_41:
    v31 = "Error reading exclusions from event stream [%d]";
LABEL_68:
    v10 = v17;
    AslLogCallPrintf(1, (unsigned int)"UndetectedInstallerParseLuafvEvent", v30, (_DWORD)v31, v17);
    goto LABEL_69;
  }
  AslLogCallPrintf(1, (unsigned int)"UndetectedInstallerParseLuafvEvent", 245, (unsigned int)"Invalid user sid.");
LABEL_14:
  v10 = 1359;
LABEL_69:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( v16 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
  return v10;
}

```

## disassembly

```asm
0x180050394  mov     rax, rsp
0x180050397  mov     [rax+20h], r9
0x18005039b  mov     [rax+18h], r8
0x18005039f  mov     [rax+10h], rdx
0x1800503a3  mov     [rax+8], rcx
0x1800503a7  push    rbx
0x1800503a8  push    rbp
0x1800503a9  push    rsi
0x1800503aa  push    rdi
0x1800503ab  push    r12
0x1800503ad  push    r13
0x1800503af  push    r14
0x1800503b1  push    r15
0x1800503b3  sub     rsp, 38h
0x1800503b7  mov     rsi, [rsp+78h+arg_28]
0x1800503bf  mov     rax, [rsi+8]
0x1800503c3  lea     r10, [rax-4]
0x1800503c7  cmp     r10, rax
0x1800503ca  ja      loc_180050918
0x1800503d0  mov     [rsi+20h], r10
0x1800503d4  mov     r9, [rsi+28h]
0x1800503d8  mov     ecx, [r9+r10]
0x1800503dc  mov     dword ptr [rsp+78h+arg_28], ecx
0x1800503e3  mov     [rsi+20h], rax
0x1800503e7  mov     ecx, 4
0x1800503ec  cmp     rax, rcx
0x1800503ef  jb      loc_180050905
0x1800503f5  lea     ebx, [rcx+4]
0x1800503f8  mov     [rsi+20h], rcx
0x1800503fc  cmp     rax, rbx
0x1800503ff  jb      loc_1800508DC
0x180050405  mov     eax, [r9+4]
0x180050409  mov     [rsi+20h], rbx
0x18005040d  xor     r14d, r14d
0x180050410  test    eax, eax
0x180050412  jnz     short loc_18005043A
0x180050414  lea     r9, aInvalidUserSid_0; "Invalid user sid length"
0x18005041b  mov     r8d, 0DEh
0x180050421  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x180050428  lea     ecx, [rbx-7]
0x18005042b  call    AslLogCallPrintf
0x180050430  mov     ebx, 54Fh
0x180050435  jmp     loc_180050944
0x18005043a  mov     rcx, gs:60h
0x180050443  mov     r8, rax; Size
0x180050446  mov     edx, ebx; Flags
0x180050448  mov     rdi, rax
0x18005044b  mov     rcx, [rcx+30h]; HeapHandle
0x18005044f  call    cs:__imp_RtlAllocateHeap
0x180050455  mov     r13, rax
0x180050458  test    rax, rax
0x18005045b  jnz     short loc_18005047E
0x18005045d  lea     r9, aErrorAllocatin_1; "Error allocating user sid."
0x180050464  mov     r8d, 0E9h
0x18005046a  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x180050471  lea     ecx, [rax+1]
0x180050474  call    AslLogCallPrintf
0x180050479  jmp     loc_180050944
0x18005047e  mov     rcx, [rsi+20h]
0x180050482  mov     r12, r14
0x180050485  mov     r15, r14
0x180050488  cmp     rcx, [rsi+8]
0x18005048c  jbe     short loc_180050498
0x18005048e  mov     eax, 0A0h
0x180050493  jmp     loc_180050860
0x180050498  lea     rax, [rcx+rdi]
0x18005049c  cmp     rax, rcx
0x18005049f  jb      short loc_18005048E
0x1800504a1  cmp     rax, [rsi+8]
0x1800504a5  ja      short loc_18005048E
0x1800504a7  mov     rdx, [rsi+28h]
0x1800504ab  mov     r8, rdi; Size
0x1800504ae  add     rdx, rcx; Src
0x1800504b1  mov     rcx, r13; void *
0x1800504b4  call    memcpy_0
0x1800504b9  mov     rax, [rsi+20h]
0x1800504bd  lea     rcx, [rax+rdi]
0x1800504c1  cmp     rcx, rax
0x1800504c4  jb      loc_180050853
0x1800504ca  mov     [rsi+20h], rcx
0x1800504ce  mov     rcx, r13; Sid
0x1800504d1  call    cs:__imp_RtlValidSid
0x1800504d7  test    al, al
0x1800504d9  jnz     short loc_180050503
0x1800504db  lea     r9, aInvalidUserSid; "Invalid user sid."
0x1800504e2  mov     r8d, 0F5h
0x1800504e8  mov     ecx, 1
0x1800504ed  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x1800504f4  call    AslLogCallPrintf
0x1800504f9  mov     ebx, 54Fh
0x1800504fe  jmp     loc_180050884
0x180050503  mov     rcx, [rsi+20h]
0x180050507  cmp     rcx, [rsi+8]
0x18005050b  ja      loc_180050841
0x180050511  lea     rdx, [rcx+2]
0x180050515  cmp     rdx, rcx
0x180050518  jb      loc_180050841
0x18005051e  cmp     rdx, [rsi+8]
0x180050522  ja      loc_180050841
0x180050528  mov     rax, [rsi+28h]
0x18005052c  movzx   ebp, word ptr [rcx+rax]
0x180050530  mov     [rsi+20h], rdx
0x180050534  test    bp, bp
0x180050537  jnz     short loc_180050548
0x180050539  lea     r9, aInvalidFileNam_0; "Invalid file name length"
0x180050540  mov     r8d, 106h
0x180050546  jmp     short loc_1800504E8
0x180050548  mov     edi, 1
0x18005054d  lea     eax, [rdi+rbp]
0x180050550  cmp     ax, bp
0x180050553  jnb     short loc_18005057A
0x180050555  mov     r8d, 110h
0x18005055b  lea     r9, aIntegerOverflo; "Integer overflow calculating filename l"...
0x180050562  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x180050569  mov     ecx, edi
0x18005056b  call    AslLogCallPrintf
0x180050570  mov     ebx, 216h
0x180050575  jmp     loc_180050884
0x18005057a  movzx   ecx, ax
0x18005057d  add     ecx, ecx
0x18005057f  cmp     ecx, 0FFFFh
0x180050585  ja      loc_180050836
0x18005058b  movzx   r8d, cx; Size
0x18005058f  mov     edx, ebx; Flags
0x180050591  mov     rcx, gs:60h
0x18005059a  mov     rcx, [rcx+30h]; HeapHandle
0x18005059e  call    cs:__imp_RtlAllocateHeap
0x1800505a4  mov     r12, rax
0x1800505a7  test    rax, rax
0x1800505aa  jnz     short loc_1800505CC
0x1800505ac  lea     r9, aErrorAllocatin; "Error allocating file name buffer."
0x1800505b3  mov     r8d, 11Dh
0x1800505b9  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x1800505c0  mov     ecx, edi
0x1800505c2  call    AslLogCallPrintf
0x1800505c7  jmp     loc_180050884
0x1800505cc  lea     r14, ds:0[rbp*2]
0x1800505d4  test    r14, r14
0x1800505d7  jz      short loc_18005061F
0x1800505d9  mov     rcx, [rsi+20h]
0x1800505dd  cmp     rcx, [rsi+8]
0x1800505e1  jbe     short loc_1800505ED
0x1800505e3  mov     eax, 0A0h
0x1800505e8  jmp     loc_180050680
0x1800505ed  lea     rax, [rcx+r14]
0x1800505f1  cmp     rax, rcx
0x1800505f4  jb      short loc_1800505E3
0x1800505f6  cmp     rax, [rsi+8]
0x1800505fa  ja      short loc_1800505E3
0x1800505fc  mov     rdx, [rsi+28h]
0x180050600  mov     r8, r14; Size
0x180050603  add     rdx, rcx; Src
0x180050606  mov     rcx, r12; void *
0x180050609  call    memcpy_0
0x18005060e  mov     rax, [rsi+20h]
0x180050612  lea     rcx, [rax+r14]
0x180050616  cmp     rcx, rax
0x180050619  jb      short loc_180050673
0x18005061b  mov     [rsi+20h], rcx
0x18005061f  xor     eax, eax
0x180050621  mov     [r14+r12], ax
0x180050626  mov     rbp, [rsi+20h]
0x18005062a  cmp     rbp, [rsi+8]
0x18005062e  ja      loc_180050826
0x180050634  lea     rcx, [rbp+2]
0x180050638  cmp     rcx, rbp
0x18005063b  jb      loc_180050826
0x180050641  cmp     rcx, [rsi+8]
0x180050645  ja      loc_180050826
0x18005064b  mov     rax, [rsi+28h]
0x18005064f  movzx   ebp, word ptr [rax+rbp]
0x180050653  mov     [rsi+20h], rcx
0x180050657  xor     r14d, r14d
0x18005065a  test    bp, bp
0x18005065d  jnz     short loc_180050694
0x18005065f  lea     r9, aInvalidFileNam_0; "Invalid file name length"
0x180050666  mov     r8d, 136h
0x18005066c  mov     ecx, edi
0x18005066e  jmp     loc_1800504ED
0x180050673  mov     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18005067b  mov     eax, 216h
0x180050680  mov     r8d, 124h
0x180050686  lea     r9, aErrorReadingEx_0; "Error reading exclusions from event str"...
0x18005068d  mov     ecx, edi
0x18005068f  jmp     loc_180050872
0x180050694  lea     eax, [rdi+rbp]
0x180050697  cmp     ax, bp
0x18005069a  jnb     short loc_1800506AE
0x18005069c  lea     r9, aIntegerOverflo_0; "Integer overflow calculating imagename "...
0x1800506a3  mov     r8d, 140h
0x1800506a9  jmp     loc_180050562
0x1800506ae  movzx   ecx, ax
0x1800506b1  add     ecx, ecx
0x1800506b3  cmp     ecx, 0FFFFh
0x1800506b9  ja      loc_180050814
0x1800506bf  movzx   r8d, cx; Size
0x1800506c3  mov     edx, ebx; Flags
0x1800506c5  mov     rcx, gs:60h
0x1800506ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800506d2  call    cs:__imp_RtlAllocateHeap
0x1800506d8  mov     r15, rax
0x1800506db  test    rax, rax
0x1800506de  jnz     short loc_1800506F2
0x1800506e0  lea     r9, aErrorAllocatin_3; "Error allocating image name buffer."
0x1800506e7  mov     r8d, 14Dh
0x1800506ed  jmp     loc_1800505B9
0x1800506f2  lea     rbx, ds:0[rbp*2]
0x1800506fa  test    rbx, rbx
0x1800506fd  jz      short loc_180050749
0x1800506ff  mov     rcx, [rsi+20h]
0x180050703  cmp     rcx, [rsi+8]
0x180050707  jbe     short loc_180050713
0x180050709  mov     eax, 0A0h
0x18005070e  jmp     loc_1800507DB
0x180050713  lea     rax, [rbx+rcx]
0x180050717  cmp     rax, rcx
0x18005071a  jb      short loc_180050709
0x18005071c  cmp     rax, [rsi+8]
0x180050720  ja      short loc_180050709
0x180050722  mov     rdx, [rsi+28h]
0x180050726  mov     r8, rbx; Size
0x180050729  add     rdx, rcx; Src
0x18005072c  mov     rcx, r15; void *
0x18005072f  call    memcpy_0
0x180050734  mov     rax, [rsi+20h]
0x180050738  lea     rcx, [rax+rbx]
0x18005073c  cmp     rcx, rax
0x18005073f  jb      loc_1800507CE
0x180050745  mov     [rsi+20h], rcx
0x180050749  mov     [rbx+r15], r14w
0x18005074e  mov     rcx, [rsi+20h]
0x180050752  add     rcx, 4
0x180050756  cmp     rcx, [rsi+8]
0x18005075a  ja      loc_1800507FD
0x180050760  lea     rdx, [rcx+4]
0x180050764  mov     [rsi+20h], rcx
0x180050768  cmp     rdx, rcx
0x18005076b  jb      short loc_1800507E6
0x18005076d  cmp     rdx, [rsi+8]
0x180050771  ja      short loc_1800507E6
0x180050773  mov     rax, [rsi+28h]
0x180050777  mov     ecx, [rcx+rax]
0x18005077a  mov     [rsi+20h], rdx
0x18005077e  mov     eax, dword ptr [rsp+78h+arg_28]
0x180050785  test    ecx, 0D0156h
0x18005078b  mov     rdx, [rsp+78h+arg_0]
0x180050793  mov     ebx, r14d
0x180050796  mov     rcx, [rsp+78h+arg_8]
0x18005079e  mov     [rdx], eax
0x1800507a0  mov     eax, r14d
0x1800507a3  setnz   al
0x1800507a6  mov     [rcx], eax
0x1800507a8  mov     rax, [rsp+78h+arg_10]
0x1800507b0  mov     [rax], r13
0x1800507b3  mov     rax, [rsp+78h+arg_18]
0x1800507bb  mov     [rax], r12
0x1800507be  mov     rax, [rsp+78h+arg_20]
0x1800507c6  mov     [rax], r15
0x1800507c9  jmp     loc_180050944
0x1800507ce  mov     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x1800507d6  mov     eax, 216h
0x1800507db  mov     r8d, 154h
0x1800507e1  jmp     loc_180050686
0x1800507e6  mov     eax, 0A0h
0x1800507eb  lea     r9, aErrorReadingDe; "Error reading desired access from event"...
0x1800507f2  mov     r8d, 166h
0x1800507f8  jmp     loc_18005068D
0x1800507fd  mov     eax, 0A0h
0x180050802  lea     r9, aErrorSettingSt; "Error setting stream position [%d]"
0x180050809  mov     r8d, 160h
0x18005080f  jmp     loc_18005068D
0x180050814  lea     r9, aIntegerOverflo_0; "Integer overflow calculating imagename "...
0x18005081b  mov     r8d, 146h
0x180050821  jmp     loc_180050562
0x180050826  mov     eax, 0A0h
0x18005082b  mov     r8d, 131h
0x180050831  jmp     loc_180050686
0x180050836  mov     r8d, 116h
0x18005083c  jmp     loc_18005055B
0x180050841  mov     eax, 0A0h
0x180050846  lea     r9, aErrorReadingEx_0; "Error reading exclusions from event str"...
0x18005084d  lea     r8d, [rax+61h]
0x180050851  jmp     short loc_18005086D
0x180050853  mov     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18005085b  mov     eax, 216h
0x180050860  lea     r9, aErrorReadingUs; "Error reading user sid [%d]"
0x180050867  mov     r8d, 0F0h
0x18005086d  mov     ecx, 1
0x180050872  lea     rdx, aUndetectedinst_2; "UndetectedInstallerParseLuafvEvent"
0x180050879  mov     [rsp+78h+var_58], eax
0x18005087d  mov     ebx, eax
0x18005087f  call    AslLogCallPrintf
0x180050884  mov     rcx, gs:60h
0x18005088d  mov     r8, r13; P
0x180050890  xor     edx, edx; Flags
0x180050892  mov     rcx, [rcx+30h]; HeapHandle
0x180050896  call    cs:__imp_RtlFreeHeap
0x18005089c  test    r12, r12
0x18005089f  jz      short loc_1800508B9
0x1800508a1  mov     rcx, gs:60h
  ... truncated ...
```
