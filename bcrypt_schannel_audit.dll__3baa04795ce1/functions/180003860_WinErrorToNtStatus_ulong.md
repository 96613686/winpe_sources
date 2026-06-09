# WinErrorToNtStatus(ulong)

- ea: `0x180003860`
- end: `0x180003b63`
- name: `?WinErrorToNtStatus@@YAJK@Z`
- size: `771`
- prototype: `__int64 __fastcall(NTSTATUS Status)`
- caller_count: `22`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001dd0`
- `0x180002bd0`
- `0x1800030a0`
- `0x18000997c`
- `0x180012780`
- `0x180012f40`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x180018b80`
- `0x180018d90`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`
- `0x1800195e0`
- `0x180019770`
- `0x180019a00`
- `0x180019b1c`

## callees

- `0x180003860`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800039e3`
- `ntdll!RtlNtStatusToDosError` at `0x1800039e3`

## pseudocode

```c
__int64 __fastcall WinErrorToNtStatus(unsigned int Status)
{
  __int64 result; // rax
  ULONG v3; // eax
  unsigned int v4; // ecx

  if ( Status > 0x103 )
  {
    if ( Status <= 0x490 )
    {
      switch ( Status )
      {
        case 0x490u:
          return 3221226021LL;
        case 0x250u:
          return 3221226011LL;
        case 0x3E6u:
          return 3221225477LL;
        case 0x3ECu:
          return 3221225485LL;
      }
    }
    else
    {
      switch ( Status )
      {
        case 0x491u:
          return 3221226098LL;
        case 0x4DBu:
          return 3221225824LL;
        case 0x54Fu:
          return 3221225701LL;
      }
    }
LABEL_33:
    v3 = RtlNtStatusToDosError(Status);
    v4 = -1073741823;
    if ( v3 != 317 )
      return Status;
    return v4;
  }
  else if ( Status == 259 )
  {
    return 2147483674LL;
  }
  else
  {
    switch ( Status )
    {
      case 0u:
        result = 0;
        break;
      case 1u:
        result = 3221225647LL;
        break;
      case 2u:
        result = 3221225524LL;
        break;
      case 3u:
        result = 3221225530LL;
        break;
      case 5u:
        result = 3221225506LL;
        break;
      case 6u:
        result = 3221225480LL;
        break;
      case 8u:
      case 0xEu:
        result = 3221225495LL;
        break;
      case 0xDu:
      case 0x17u:
        result = 3221225534LL;
        break;
      case 0x12u:
        result = 2147483654LL;
        break;
      case 0x1Fu:
        result = 3221225473LL;
        break;
      case 0x20u:
        result = 3221225539LL;
        break;
      case 0x32u:
        result = 3221225474LL;
        break;
      case 0x57u:
        return 3221225485LL;
      case 0x7Au:
        result = 3221225507LL;
        break;
      case 0x7Bu:
        result = 3221225523LL;
        break;
      case 0xA1u:
        result = 3221225529LL;
        break;
      case 0xB7u:
        result = 3221225525LL;
        break;
      case 0xEAu:
        result = 2147483653LL;
        break;
      default:
        goto LABEL_33;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003860  push    rbx
0x180003862  sub     rsp, 20h
0x180003866  mov     ebx, ecx
0x180003868  cmp     ecx, 103h
0x18000386e  ja      short loc_1800038AD
0x180003870  jz      loc_1800039C9
0x180003876  cmp     ebx, 0EAh; switch 235 cases
0x18000387c  ja      def_18000389B; jumptable 000000018000389B default case, cases 4,7,9-12,15-17,19-22,24-30,33-49,51-86,88-121,124-160,162-182,184-233
0x180003882  lea     rdx, __ImageBase
0x180003889  movzx   eax, ds:(byte_180003A78 - 180000000h)[rdx+rbx]
0x180003891  mov     ecx, ds:(jpt_18000389B - 180000000h)[rdx+rax*4]
0x180003898  add     rcx, rdx
0x18000389b  jmp     rcx; switch jump
0x1800038a1  mov     eax, 0C0000017h; jumptable 000000018000389B cases 8,14
0x1800038a6  add     rsp, 20h
0x1800038aa  pop     rbx
0x1800038ab  retn
0x1800038ad  cmp     ebx, 490h
0x1800038b3  jbe     short loc_1800038DC
0x1800038b5  mov     eax, ebx
0x1800038b7  sub     eax, 491h
0x1800038bc  jz      short loc_180003932
0x1800038be  sub     eax, 4Ah ; 'J'
0x1800038c1  jz      loc_180003A05
0x1800038c7  cmp     eax, 74h ; 't'
0x1800038ca  jnz     def_18000389B; jumptable 000000018000389B default case, cases 4,7,9-12,15-17,19-22,24-30,33-49,51-86,88-121,124-160,162-182,184-233
0x1800038d0  mov     eax, 0C00000E5h
0x1800038d5  add     rsp, 20h
0x1800038d9  pop     rbx
0x1800038da  retn
0x1800038dc  jz      short loc_180003926
0x1800038de  mov     eax, ebx
0x1800038e0  sub     eax, 250h
0x1800038e5  jz      loc_1800039D5
0x1800038eb  sub     eax, 196h
0x1800038f0  jnz     loc_180003A1D
0x1800038f6  mov     eax, 0C0000005h
0x1800038fb  add     rsp, 20h
0x1800038ff  pop     rbx
0x180003900  retn
0x180003902  mov     eax, 0C0000022h; jumptable 000000018000389B case 5
0x180003907  add     rsp, 20h
0x18000390b  pop     rbx
0x18000390c  retn
0x18000390e  mov     eax, 0C0000039h; jumptable 000000018000389B case 161
0x180003913  add     rsp, 20h
0x180003917  pop     rbx
0x180003918  retn
0x18000391a  mov     eax, 0C000003Ah; jumptable 000000018000389B case 3
0x18000391f  add     rsp, 20h
0x180003923  pop     rbx
0x180003924  retn
0x180003926  mov     eax, 0C0000225h
0x18000392b  add     rsp, 20h
0x18000392f  pop     rbx
0x180003930  retn
0x180003932  mov     eax, 0C0000272h
0x180003937  jmp     loc_1800038A6
0x18000393c  xor     eax, eax; jumptable 000000018000389B case 0
0x18000393e  add     rsp, 20h
0x180003942  pop     rbx
0x180003943  retn
0x180003945  mov     eax, 0C0000001h; jumptable 000000018000389B case 31
0x18000394a  add     rsp, 20h
0x18000394e  pop     rbx
0x18000394f  retn
0x180003951  mov     eax, 0C0000043h; jumptable 000000018000389B case 32
0x180003956  add     rsp, 20h
0x18000395a  pop     rbx
0x18000395b  retn
0x18000395d  mov     eax, 0C0000002h; jumptable 000000018000389B case 50
0x180003962  add     rsp, 20h
0x180003966  pop     rbx
0x180003967  retn
0x180003969  mov     eax, 0C00000AFh; jumptable 000000018000389B case 1
0x18000396e  add     rsp, 20h
0x180003972  pop     rbx
0x180003973  retn
0x180003975  mov     eax, 0C0000033h; jumptable 000000018000389B case 123
0x18000397a  add     rsp, 20h
0x18000397e  pop     rbx
0x18000397f  retn
0x180003981  mov     eax, 0C0000008h; jumptable 000000018000389B case 6
0x180003986  add     rsp, 20h
0x18000398a  pop     rbx
0x18000398b  retn
0x18000398d  mov     eax, 0C0000023h; jumptable 000000018000389B case 122
0x180003992  add     rsp, 20h
0x180003996  pop     rbx
0x180003997  retn
0x180003999  mov     eax, 80000005h; jumptable 000000018000389B case 234
0x18000399e  add     rsp, 20h
0x1800039a2  pop     rbx
0x1800039a3  retn
0x1800039a5  mov     eax, 80000006h; jumptable 000000018000389B case 18
0x1800039aa  add     rsp, 20h
0x1800039ae  pop     rbx
0x1800039af  retn
0x1800039b1  mov     eax, 0C0000035h; jumptable 000000018000389B case 183
0x1800039b6  add     rsp, 20h
0x1800039ba  pop     rbx
0x1800039bb  retn
0x1800039bd  mov     eax, 0C0000034h; jumptable 000000018000389B case 2
0x1800039c2  add     rsp, 20h
0x1800039c6  pop     rbx
0x1800039c7  retn
0x1800039c9  mov     eax, 8000001Ah
0x1800039ce  add     rsp, 20h
0x1800039d2  pop     rbx
0x1800039d3  retn
0x1800039d5  mov     eax, 0C000021Bh
0x1800039da  add     rsp, 20h
0x1800039de  pop     rbx
0x1800039df  retn
0x1800039e1  mov     ecx, ebx; jumptable 000000018000389B default case, cases 4,7,9-12,15-17,19-22,24-30,33-49,51-86,88-121,124-160,162-182,184-233
0x1800039e3  call    cs:__imp_RtlNtStatusToDosError
0x1800039ea  nop     dword ptr [rax+rax+00h]
0x1800039ef  cmp     eax, 13Dh
0x1800039f4  mov     ecx, 0C0000001h
0x1800039f9  cmovnz  ecx, ebx
0x1800039fc  mov     eax, ecx
0x1800039fe  add     rsp, 20h
0x180003a02  pop     rbx
0x180003a03  retn
0x180003a05  mov     eax, 0C0000160h
0x180003a0a  add     rsp, 20h
0x180003a0e  pop     rbx
0x180003a0f  retn
0x180003a11  mov     eax, 0C000003Eh; jumptable 000000018000389B cases 13,23
0x180003a16  add     rsp, 20h
0x180003a1a  pop     rbx
0x180003a1b  retn
0x180003a1d  cmp     eax, 6
0x180003a20  jnz     short def_18000389B; jumptable 000000018000389B default case, cases 4,7,9-12,15-17,19-22,24-30,33-49,51-86,88-121,124-160,162-182,184-233
0x180003a22  mov     eax, 0C000000Dh; jumptable 000000018000389B case 87
0x180003a27  jmp     loc_1800038A6
```
