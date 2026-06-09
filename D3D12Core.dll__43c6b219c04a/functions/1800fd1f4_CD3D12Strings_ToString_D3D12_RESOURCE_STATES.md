# CD3D12Strings::ToString(D3D12_RESOURCE_STATES)

- ea: `0x1800fd1f4`
- end: `0x1800fd51f`
- name: `?ToString@CD3D12Strings@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4D3D12_RESOURCE_STATES@@@Z`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800641b4`

## callees

- `0x18009fa70`
- `0x18009fd4c`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x1800ec084`
- `0x1800fd1f4`
- `0x180102704`

## string_xrefs

- `0x1800fd2d3`: `D3D12_RESOURCE_STATE_DEPTH_WRITE`
- `0x1800fd2ba`: `D3D12_RESOURCE_STATE_UNORDERED_ACCESS`
- `0x1800fd232`: `D3D12_RESOURCE_STATE_[COMMON|PRESENT]`
- `0x1800fd253`: `D3D12_RESOURCE_STATE_GENERIC_READ`
- `0x1800fd36e`: `D3D12_RESOURCE_STATE_COPY_DEST`
- `0x1800fd389`: `D3D12_RESOURCE_STATE_COPY_SOURCE`
- `0x1800fd2ec`: `D3D12_RESOURCE_STATE_DEPTH_READ`
- `0x1800fd446`: `D3D12_RESOURCE_STATE_VIDEO_ENCODE_READ`
- `0x1800fd42b`: `D3D12_RESOURCE_STATE_VIDEO_PROCESS_WRITE`
- `0x1800fd461`: `D3D12_RESOURCE_STATE_VIDEO_ENCODE_WRITE`
- `0x1800fd3da`: `D3D12_RESOURCE_STATE_VIDEO_DECODE_READ`
- `0x1800fd410`: `D3D12_RESOURCE_STATE_VIDEO_PROCESS_READ`
- `0x1800fd3f5`: `D3D12_RESOURCE_STATE_VIDEO_DECODE_WRITE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CD3D12Strings::ToString(__int64 a1, int a2)
{
  bool v4; // bl
  _QWORD *v5; // rdx
  _BYTE v7[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[232]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[4]; // [rsp+120h] [rbp+20h] BYREF

  std::ostringstream::ostringstream(v7);
  if ( a2 )
  {
    if ( (a2 & 0xAC3) == 0xAC3 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_GENERIC_READ");
      a2 &= 0xFFFFF53C;
    }
    if ( (a2 & 1) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER");
      a2 &= ~1u;
    }
    if ( (a2 & 2) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_INDEX_BUFFER");
      a2 &= ~2u;
    }
    if ( (a2 & 4) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_RENDER_TARGET");
      a2 &= ~4u;
    }
    if ( (a2 & 8) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_UNORDERED_ACCESS");
      a2 &= ~8u;
    }
    if ( (a2 & 0x10) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_DEPTH_WRITE");
      a2 &= ~0x10u;
    }
    if ( (a2 & 0x20) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_DEPTH_READ");
      a2 &= ~0x20u;
    }
    if ( (a2 & 0x40) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE");
      a2 &= ~0x40u;
    }
    if ( (a2 & 0x80u) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE");
      a2 &= ~0x80u;
    }
    if ( (a2 & 0x100) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_STREAM_OUT");
      a2 &= ~0x100u;
    }
    if ( (a2 & 0x200) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_INDIRECT_ARGUMENT");
      a2 &= ~0x200u;
    }
    if ( (a2 & 0x400) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_COPY_DEST");
      a2 &= ~0x400u;
    }
    if ( (a2 & 0x800) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_COPY_SOURCE");
      a2 &= ~0x800u;
    }
    if ( (a2 & 0x1000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_RESOLVE_DEST");
      a2 &= ~0x1000u;
    }
    if ( (a2 & 0x2000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_RESOLVE_SOURCE");
      a2 &= ~0x2000u;
    }
    if ( (a2 & 0x10000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_DECODE_READ");
      a2 &= ~0x10000u;
    }
    if ( (a2 & 0x20000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_DECODE_WRITE");
      a2 &= ~0x20000u;
    }
    if ( (a2 & 0x40000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_PROCESS_READ");
      a2 &= ~0x40000u;
    }
    if ( (a2 & 0x80000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_PROCESS_WRITE");
      a2 &= ~0x80000u;
    }
    if ( (a2 & 0x200000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_ENCODE_READ");
      a2 &= ~0x200000u;
    }
    if ( (a2 & 0x800000) != 0 )
    {
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_VIDEO_ENCODE_WRITE");
      a2 &= ~0x800000u;
    }
    if ( (a2 & 0x400000) != 0 )
      CD3D12Strings::AppendFlagString(v7, "D3D12_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE");
    std::stringbuf::str(v8, v9);
    v4 = v9[2] == 0;
    std::string::_Tidy_deallocate(v9);
    if ( v4 )
      std::operator<<<std::char_traits<char>>(v7, "0");
    std::stringbuf::str(v8, v9);
    v5 = v9;
    if ( v9[3] > 0xFu )
      v5 = (_QWORD *)v9[0];
    std::string::string(a1, v5);
    std::string::_Tidy_deallocate(v9);
  }
  else
  {
    std::string::string(a1, "D3D12_RESOURCE_STATE_[COMMON|PRESENT]");
  }
  std::ostringstream::`vbase destructor'(v7);
  return a1;
}

```

## disassembly

```asm
0x1800fd1f4  mov     [rsp-8+arg_8], rbx
0x1800fd1f9  mov     [rsp-8+arg_10], rdi
0x1800fd1fe  push    rbp
0x1800fd1ff  lea     rbp, [rsp-50h]
0x1800fd204  sub     rsp, 150h
0x1800fd20b  mov     rax, cs:__security_cookie
0x1800fd212  xor     rax, rsp
0x1800fd215  mov     [rbp+50h+var_10], rax
0x1800fd219  mov     ebx, edx
0x1800fd21b  mov     rdi, rcx
0x1800fd21e  mov     [rsp+150h+var_128], rcx
0x1800fd223  lea     rcx, [rsp+150h+var_120]
0x1800fd228  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800fd22d  nop
0x1800fd22e  test    ebx, ebx
0x1800fd230  jnz     short loc_1800FD246
0x1800fd232  lea     rdx, aD3d12ResourceS_8; "D3D12_RESOURCE_STATE_[COMMON|PRESENT]"
0x1800fd239  mov     rcx, rdi
0x1800fd23c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800fd241  jmp     loc_1800FD4F1
0x1800fd246  mov     eax, ebx
0x1800fd248  mov     ecx, 0AC3h
0x1800fd24d  and     eax, ecx
0x1800fd24f  cmp     eax, ecx
0x1800fd251  jnz     short loc_1800FD26A
0x1800fd253  lea     rdx, aD3d12ResourceS_14; "D3D12_RESOURCE_STATE_GENERIC_READ"
0x1800fd25a  lea     rcx, [rsp+150h+var_120]
0x1800fd25f  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd264  and     ebx, 0FFFFF53Ch
0x1800fd26a  test    bl, 1
0x1800fd26d  jz      short loc_1800FD283
0x1800fd26f  lea     rdx, aD3d12ResourceS_5; "D3D12_RESOURCE_STATE_VERTEX_AND_CONSTAN"...
0x1800fd276  lea     rcx, [rsp+150h+var_120]
0x1800fd27b  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd280  and     ebx, 0FFFFFFFEh
0x1800fd283  test    bl, 2
0x1800fd286  jz      short loc_1800FD29C
0x1800fd288  lea     rdx, aD3d12ResourceS_26; "D3D12_RESOURCE_STATE_INDEX_BUFFER"
0x1800fd28f  lea     rcx, [rsp+150h+var_120]
0x1800fd294  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd299  and     ebx, 0FFFFFFFDh
0x1800fd29c  test    bl, 4
0x1800fd29f  jz      short loc_1800FD2B5
0x1800fd2a1  lea     rdx, aD3d12ResourceS_29; "D3D12_RESOURCE_STATE_RENDER_TARGET"
0x1800fd2a8  lea     rcx, [rsp+150h+var_120]
0x1800fd2ad  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd2b2  and     ebx, 0FFFFFFFBh
0x1800fd2b5  test    bl, 8
0x1800fd2b8  jz      short loc_1800FD2CE
0x1800fd2ba  lea     rdx, aD3d12ResourceS_21; "D3D12_RESOURCE_STATE_UNORDERED_ACCESS"
0x1800fd2c1  lea     rcx, [rsp+150h+var_120]
0x1800fd2c6  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd2cb  and     ebx, 0FFFFFFF7h
0x1800fd2ce  test    bl, 10h
0x1800fd2d1  jz      short loc_1800FD2E7
0x1800fd2d3  lea     rdx, aD3d12ResourceS; "D3D12_RESOURCE_STATE_DEPTH_WRITE"
0x1800fd2da  lea     rcx, [rsp+150h+var_120]
0x1800fd2df  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd2e4  and     ebx, 0FFFFFFEFh
0x1800fd2e7  test    bl, 20h
0x1800fd2ea  jz      short loc_1800FD300
0x1800fd2ec  lea     rdx, aD3d12ResourceS_19; "D3D12_RESOURCE_STATE_DEPTH_READ"
0x1800fd2f3  lea     rcx, [rsp+150h+var_120]
0x1800fd2f8  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd2fd  and     ebx, 0FFFFFFDFh
0x1800fd300  test    bl, 40h
0x1800fd303  jz      short loc_1800FD319
0x1800fd305  lea     rdx, aD3d12ResourceS_23; "D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_R"...
0x1800fd30c  lea     rcx, [rsp+150h+var_120]
0x1800fd311  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd316  and     ebx, 0FFFFFFBFh
0x1800fd319  test    bl, bl
0x1800fd31b  jns     short loc_1800FD332
0x1800fd31d  lea     rdx, aD3d12ResourceS_18; "D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOU"...
0x1800fd324  lea     rcx, [rsp+150h+var_120]
0x1800fd329  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd32e  btr     ebx, 7
0x1800fd332  bt      ebx, 8
0x1800fd336  jnb     short loc_1800FD34D
0x1800fd338  lea     rdx, aD3d12ResourceS_27; "D3D12_RESOURCE_STATE_STREAM_OUT"
0x1800fd33f  lea     rcx, [rsp+150h+var_120]
0x1800fd344  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd349  btr     ebx, 8
0x1800fd34d  bt      ebx, 9
0x1800fd351  jnb     short loc_1800FD368
0x1800fd353  lea     rdx, aD3d12ResourceS_20; "D3D12_RESOURCE_STATE_INDIRECT_ARGUMENT"
0x1800fd35a  lea     rcx, [rsp+150h+var_120]
0x1800fd35f  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd364  btr     ebx, 9
0x1800fd368  bt      ebx, 0Ah
0x1800fd36c  jnb     short loc_1800FD383
0x1800fd36e  lea     rdx, aD3d12ResourceS_9; "D3D12_RESOURCE_STATE_COPY_DEST"
0x1800fd375  lea     rcx, [rsp+150h+var_120]
0x1800fd37a  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd37f  btr     ebx, 0Ah
0x1800fd383  bt      ebx, 0Bh
0x1800fd387  jnb     short loc_1800FD39E
0x1800fd389  lea     rdx, aD3d12ResourceS_13; "D3D12_RESOURCE_STATE_COPY_SOURCE"
0x1800fd390  lea     rcx, [rsp+150h+var_120]
0x1800fd395  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd39a  btr     ebx, 0Bh
0x1800fd39e  bt      ebx, 0Ch
0x1800fd3a2  jnb     short loc_1800FD3B9
0x1800fd3a4  lea     rdx, aD3d12ResourceS_15; "D3D12_RESOURCE_STATE_RESOLVE_DEST"
0x1800fd3ab  lea     rcx, [rsp+150h+var_120]
0x1800fd3b0  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd3b5  btr     ebx, 0Ch
0x1800fd3b9  bt      ebx, 0Dh
0x1800fd3bd  jnb     short loc_1800FD3D4
0x1800fd3bf  lea     rdx, aD3d12ResourceS_24; "D3D12_RESOURCE_STATE_RESOLVE_SOURCE"
0x1800fd3c6  lea     rcx, [rsp+150h+var_120]
0x1800fd3cb  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd3d0  btr     ebx, 0Dh
0x1800fd3d4  bt      ebx, 10h
0x1800fd3d8  jnb     short loc_1800FD3EF
0x1800fd3da  lea     rdx, aD3d12ResourceS_0; "D3D12_RESOURCE_STATE_VIDEO_DECODE_READ"
0x1800fd3e1  lea     rcx, [rsp+150h+var_120]
0x1800fd3e6  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd3eb  btr     ebx, 10h
0x1800fd3ef  bt      ebx, 11h
0x1800fd3f3  jnb     short loc_1800FD40A
0x1800fd3f5  lea     rdx, aD3d12ResourceS_16; "D3D12_RESOURCE_STATE_VIDEO_DECODE_WRITE"
0x1800fd3fc  lea     rcx, [rsp+150h+var_120]
0x1800fd401  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd406  btr     ebx, 11h
0x1800fd40a  bt      ebx, 12h
0x1800fd40e  jnb     short loc_1800FD425
0x1800fd410  lea     rdx, aD3d12ResourceS_12; "D3D12_RESOURCE_STATE_VIDEO_PROCESS_READ"
0x1800fd417  lea     rcx, [rsp+150h+var_120]
0x1800fd41c  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd421  btr     ebx, 12h
0x1800fd425  bt      ebx, 13h
0x1800fd429  jnb     short loc_1800FD440
0x1800fd42b  lea     rdx, aD3d12ResourceS_3; "D3D12_RESOURCE_STATE_VIDEO_PROCESS_WRIT"...
0x1800fd432  lea     rcx, [rsp+150h+var_120]
0x1800fd437  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd43c  btr     ebx, 13h
0x1800fd440  bt      ebx, 15h
0x1800fd444  jnb     short loc_1800FD45B
0x1800fd446  lea     rdx, aD3d12ResourceS_2; "D3D12_RESOURCE_STATE_VIDEO_ENCODE_READ"
0x1800fd44d  lea     rcx, [rsp+150h+var_120]
0x1800fd452  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd457  btr     ebx, 15h
0x1800fd45b  bt      ebx, 17h
0x1800fd45f  jnb     short loc_1800FD476
0x1800fd461  lea     rdx, aD3d12ResourceS_4; "D3D12_RESOURCE_STATE_VIDEO_ENCODE_WRITE"
0x1800fd468  lea     rcx, [rsp+150h+var_120]
0x1800fd46d  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd472  btr     ebx, 17h
0x1800fd476  bt      ebx, 16h
0x1800fd47a  jnb     short loc_1800FD48D
0x1800fd47c  lea     rdx, aD3d12ResourceS_11; "D3D12_RESOURCE_STATE_RAYTRACING_ACCELER"...
0x1800fd483  lea     rcx, [rsp+150h+var_120]
0x1800fd488  call    ?AppendFlagString@CD3D12Strings@@YAXAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CD3D12Strings::AppendFlagString(std::ostringstream &,char const *)
0x1800fd48d  lea     rdx, [rbp+50h+var_30]
0x1800fd491  lea     rcx, [rsp+150h+var_118]
0x1800fd496  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800fd49b  cmp     [rbp+50h+var_20], 0
0x1800fd4a0  setz    bl
0x1800fd4a3  lea     rcx, [rbp+50h+var_30]
0x1800fd4a7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fd4ac  test    bl, bl
0x1800fd4ae  jz      short loc_1800FD4C1
0x1800fd4b0  lea     rdx, a0; "0"
0x1800fd4b7  lea     rcx, [rsp+150h+var_120]
0x1800fd4bc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800fd4c1  lea     rdx, [rbp+50h+var_30]
0x1800fd4c5  lea     rcx, [rsp+150h+var_118]
0x1800fd4ca  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800fd4cf  nop
0x1800fd4d0  lea     rdx, [rbp+50h+var_30]
0x1800fd4d4  cmp     [rbp+50h+var_18], 0Fh
0x1800fd4d9  cmova   rdx, [rbp+50h+var_30]
0x1800fd4de  mov     rcx, rdi
0x1800fd4e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800fd4e6  nop
0x1800fd4e7  lea     rcx, [rbp+50h+var_30]
0x1800fd4eb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fd4f0  nop
0x1800fd4f1  lea     rcx, [rsp+150h+var_120]
0x1800fd4f6  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1800fd4fb  mov     rax, rdi
0x1800fd4fe  mov     rcx, [rbp+50h+var_10]
0x1800fd502  xor     rcx, rsp; StackCookie
0x1800fd505  call    __security_check_cookie
0x1800fd50a  lea     r11, [rsp+150h+var_s0]
0x1800fd512  mov     rbx, [r11+18h]
0x1800fd516  mov     rdi, [r11+20h]
0x1800fd51a  mov     rsp, r11
0x1800fd51d  pop     rbp
0x1800fd51e  retn
```
