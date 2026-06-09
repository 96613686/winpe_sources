# __abi_CustomToString(Windows::Web::WebErrorStatus *)

- ea: `0x14001d710`
- end: `0x14001ed75`
- name: `?__abi_CustomToString@@YAPE$AAVString@Platform@@PEAW4WebErrorStatus@Web@Windows@@@Z`
- size: `5733`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a120`

## callees

- `0x1400039aa`
- `0x1400039c2`
- `0x1400086b0`
- `0x14001d710`
- `0x140031960`

## string_xrefs

- `0x14001d8d4`: `CertificateCommonNameIsIncorrect`
- `0x14001e1c6`: `MovedPermanently`
- `0x14001e04a`: `TemporaryRedirect`
- `0x14001e5e5`: `RequestUriTooLong`
- `0x14001e8c6`: `ServiceUnavailable`

## pseudocode

```c
HSTRING __fastcall __abi_CustomToString(int *a1)
{
  int v1; // edx
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  HRESULT v33; // eax
  HRESULT v34; // eax
  HRESULT v35; // eax
  HRESULT v36; // eax
  int v37; // edx
  int v38; // edx
  int v39; // edx
  int v40; // edx
  HRESULT v41; // eax
  HRESULT v42; // eax
  HRESULT v43; // eax
  HRESULT v44; // eax
  HRESULT v45; // eax
  HRESULT v46; // eax
  HRESULT v47; // eax
  HRESULT v48; // eax
  HRESULT v49; // eax
  HRESULT v50; // eax
  HRESULT v51; // eax
  HRESULT v52; // eax
  int v53; // edx
  int v54; // edx
  int v55; // edx
  int v56; // edx
  HRESULT v57; // eax
  HRESULT v58; // eax
  HRESULT v59; // eax
  HRESULT v60; // eax
  HRESULT v61; // eax
  HRESULT v62; // eax
  HRESULT v63; // eax
  HRESULT v64; // eax
  HRESULT v65; // eax
  HRESULT v66; // eax
  HRESULT v67; // eax
  HRESULT v68; // eax
  int v69; // edx
  int v70; // edx
  int v71; // edx
  int v72; // edx
  int v73; // edx
  int v74; // edx
  HRESULT v75; // eax
  HRESULT v76; // eax
  HRESULT v77; // eax
  HRESULT v78; // eax
  HRESULT v79; // eax
  HRESULT v80; // eax
  HRESULT v81; // eax
  HRESULT v82; // eax
  HRESULT v83; // eax
  HRESULT v84; // eax
  HRESULT v85; // eax
  HRESULT v86; // eax
  HRESULT v87; // eax
  HRESULT v88; // eax
  HRESULT v89; // eax
  HRESULT v90; // eax
  int v91; // edx
  int v92; // edx
  int v93; // edx
  int v94; // edx
  int v95; // edx
  int v96; // edx
  HRESULT v97; // eax
  HRESULT v98; // eax
  HRESULT v99; // eax
  HRESULT v100; // eax
  HRESULT v101; // eax
  HRESULT v102; // eax
  HRESULT v103; // eax
  HRESULT v104; // eax
  HRESULT v105; // eax
  HRESULT v106; // eax
  HRESULT v107; // eax
  HRESULT v108; // eax
  HRESULT v109; // eax
  HRESULT v110; // eax
  HRESULT v111; // eax
  HRESULT v112; // eax
  int v113; // edx
  int v114; // edx
  int v115; // edx
  int v116; // edx
  int v117; // edx
  int v118; // edx
  HRESULT v119; // eax
  HRESULT v120; // eax
  HRESULT v121; // eax
  HRESULT v122; // eax
  HRESULT v123; // eax
  HRESULT v124; // eax
  HRESULT v125; // eax
  HRESULT v126; // eax
  HRESULT v127; // eax
  HRESULT v128; // eax
  HRESULT v129; // eax
  HRESULT v130; // eax
  HRESULT v131; // eax
  HRESULT v132; // eax
  HRESULT v133; // eax
  HRESULT v134; // eax
  int v135; // edx
  int v136; // edx
  int v137; // edx
  int v138; // edx
  int v139; // edx
  HRESULT v140; // eax
  HRESULT v141; // eax
  HRESULT v142; // eax
  HRESULT v143; // eax
  HRESULT v144; // eax
  HRESULT v145; // eax
  HRESULT v146; // eax
  HRESULT v147; // eax
  HRESULT v148; // eax
  HRESULT v149; // eax
  HRESULT v150; // eax
  HRESULT v151; // eax
  HRESULT v152; // eax
  HRESULT v153; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-10h] BYREF

  v1 = *a1;
  if ( *a1 > 300 )
  {
    if ( v1 > 409 )
    {
      if ( v1 > 417 )
      {
        v135 = v1 - 500;
        if ( !v135 )
        {
          newString = 0;
          v152 = WindowsCreateStringReference_0(L"InternalServerError", 0x13u, &hstringHeader, &newString);
          if ( v152 < 0 )
            __abi_WinRTraiseException(v152);
          if ( !newString )
            return 0;
          string = 0;
          v153 = WindowsDuplicateString_0(newString, &string);
          if ( v153 < 0 )
            __abi_WinRTraiseException(v153);
          return string;
        }
        v136 = v135 - 1;
        if ( !v136 )
        {
          newString = 0;
          v150 = WindowsCreateStringReference_0(L"NotImplemented", 0xEu, &hstringHeader, &newString);
          if ( v150 < 0 )
            __abi_WinRTraiseException(v150);
          if ( !newString )
            return 0;
          string = 0;
          v151 = WindowsDuplicateString_0(newString, &string);
          if ( v151 < 0 )
            __abi_WinRTraiseException(v151);
          return string;
        }
        v137 = v136 - 1;
        if ( !v137 )
        {
          newString = 0;
          v148 = WindowsCreateStringReference_0(L"BadGateway", 0xAu, &hstringHeader, &newString);
          if ( v148 < 0 )
            __abi_WinRTraiseException(v148);
          if ( !newString )
            return 0;
          string = 0;
          v149 = WindowsDuplicateString_0(newString, &string);
          if ( v149 < 0 )
            __abi_WinRTraiseException(v149);
          return string;
        }
        v138 = v137 - 1;
        if ( !v138 )
        {
          newString = 0;
          v146 = WindowsCreateStringReference_0(L"ServiceUnavailable", 0x12u, &hstringHeader, &newString);
          if ( v146 < 0 )
            __abi_WinRTraiseException(v146);
          if ( !newString )
            return 0;
          string = 0;
          v147 = WindowsDuplicateString_0(newString, &string);
          if ( v147 < 0 )
            __abi_WinRTraiseException(v147);
          return string;
        }
        v139 = v138 - 1;
        if ( !v139 )
        {
          newString = 0;
          v144 = WindowsCreateStringReference_0(L"GatewayTimeout", 0xEu, &hstringHeader, &newString);
          if ( v144 < 0 )
            __abi_WinRTraiseException(v144);
          if ( !newString )
            return 0;
          string = 0;
          v145 = WindowsDuplicateString_0(newString, &string);
          if ( v145 < 0 )
            __abi_WinRTraiseException(v145);
          return string;
        }
        if ( v139 == 1 )
        {
          newString = 0;
          v142 = WindowsCreateStringReference_0(L"HttpVersionNotSupported", 0x17u, &hstringHeader, &newString);
          if ( v142 < 0 )
            __abi_WinRTraiseException(v142);
          if ( !newString )
            return 0;
          string = 0;
          v143 = WindowsDuplicateString_0(newString, &string);
          if ( v143 < 0 )
            __abi_WinRTraiseException(v143);
          return string;
        }
      }
      else
      {
        if ( v1 == 417 )
        {
          newString = 0;
          v133 = WindowsCreateStringReference_0(L"ExpectationFailed", 0x11u, &hstringHeader, &newString);
          if ( v133 < 0 )
            __abi_WinRTraiseException(v133);
          if ( !newString )
            return 0;
          string = 0;
          v134 = WindowsDuplicateString_0(newString, &string);
          if ( v134 < 0 )
            __abi_WinRTraiseException(v134);
          return string;
        }
        v113 = v1 - 410;
        if ( !v113 )
        {
          newString = 0;
          v131 = WindowsCreateStringReference_0(L"Gone", 4u, &hstringHeader, &newString);
          if ( v131 < 0 )
            __abi_WinRTraiseException(v131);
          if ( !newString )
            return 0;
          string = 0;
          v132 = WindowsDuplicateString_0(newString, &string);
          if ( v132 < 0 )
            __abi_WinRTraiseException(v132);
          return string;
        }
        v114 = v113 - 1;
        if ( !v114 )
        {
          newString = 0;
          v129 = WindowsCreateStringReference_0(L"LengthRequired", 0xEu, &hstringHeader, &newString);
          if ( v129 < 0 )
            __abi_WinRTraiseException(v129);
          if ( !newString )
            return 0;
          string = 0;
          v130 = WindowsDuplicateString_0(newString, &string);
          if ( v130 < 0 )
            __abi_WinRTraiseException(v130);
          return string;
        }
        v115 = v114 - 1;
        if ( !v115 )
        {
          newString = 0;
          v127 = WindowsCreateStringReference_0(L"PreconditionFailed", 0x12u, &hstringHeader, &newString);
          if ( v127 < 0 )
            __abi_WinRTraiseException(v127);
          if ( !newString )
            return 0;
          string = 0;
          v128 = WindowsDuplicateString_0(newString, &string);
          if ( v128 < 0 )
            __abi_WinRTraiseException(v128);
          return string;
        }
        v116 = v115 - 1;
        if ( !v116 )
        {
          newString = 0;
          v125 = WindowsCreateStringReference_0(L"RequestEntityTooLarge", 0x15u, &hstringHeader, &newString);
          if ( v125 < 0 )
            __abi_WinRTraiseException(v125);
          if ( !newString )
            return 0;
          string = 0;
          v126 = WindowsDuplicateString_0(newString, &string);
          if ( v126 < 0 )
            __abi_WinRTraiseException(v126);
          return string;
        }
        v117 = v116 - 1;
        if ( !v117 )
        {
          newString = 0;
          v123 = WindowsCreateStringReference_0(L"RequestUriTooLong", 0x11u, &hstringHeader, &newString);
          if ( v123 < 0 )
            __abi_WinRTraiseException(v123);
          if ( !newString )
            return 0;
          string = 0;
          v124 = WindowsDuplicateString_0(newString, &string);
          if ( v124 < 0 )
            __abi_WinRTraiseException(v124);
          return string;
        }
        v118 = v117 - 1;
        if ( !v118 )
        {
          newString = 0;
          v121 = WindowsCreateStringReference_0(L"UnsupportedMediaType", 0x14u, &hstringHeader, &newString);
          if ( v121 < 0 )
            __abi_WinRTraiseException(v121);
          if ( !newString )
            return 0;
          string = 0;
          v122 = WindowsDuplicateString_0(newString, &string);
          if ( v122 < 0 )
            __abi_WinRTraiseException(v122);
          return string;
        }
        if ( v118 == 1 )
        {
          newString = 0;
          v119 = WindowsCreateStringReference_0(L"RequestedRangeNotSatisfiable", 0x1Cu, &hstringHeader, &newString);
          if ( v119 < 0 )
            __abi_WinRTraiseException(v119);
          if ( !newString )
            return 0;
          string = 0;
          v120 = WindowsDuplicateString_0(newString, &string);
          if ( v120 < 0 )
            __abi_WinRTraiseException(v120);
          return string;
        }
      }
    }
    else
    {
      if ( v1 == 409 )
      {
        newString = 0;
        v111 = WindowsCreateStringReference_0(L"Conflict", 8u, &hstringHeader, &newString);
        if ( v111 < 0 )
          __abi_WinRTraiseException(v111);
        if ( !newString )
          return 0;
        string = 0;
        v112 = WindowsDuplicateString_0(newString, &string);
        if ( v112 < 0 )
          __abi_WinRTraiseException(v112);
        return string;
      }
      if ( v1 > 401 )
      {
        v91 = v1 - 402;
        if ( !v91 )
        {
          newString = 0;
          v109 = WindowsCreateStringReference_0(L"PaymentRequired", 0xFu, &hstringHeader, &newString);
          if ( v109 < 0 )
            __abi_WinRTraiseException(v109);
          if ( !newString )
            return 0;
          string = 0;
          v110 = WindowsDuplicateString_0(newString, &string);
          if ( v110 < 0 )
            __abi_WinRTraiseException(v110);
          return string;
        }
        v92 = v91 - 1;
        if ( !v92 )
        {
          newString = 0;
          v107 = WindowsCreateStringReference_0(L"Forbidden", 9u, &hstringHeader, &newString);
          if ( v107 < 0 )
            __abi_WinRTraiseException(v107);
          if ( !newString )
            return 0;
          string = 0;
          v108 = WindowsDuplicateString_0(newString, &string);
          if ( v108 < 0 )
            __abi_WinRTraiseException(v108);
          return string;
        }
        v93 = v92 - 1;
        if ( !v93 )
        {
          newString = 0;
          v105 = WindowsCreateStringReference_0(L"NotFound", 8u, &hstringHeader, &newString);
          if ( v105 < 0 )
            __abi_WinRTraiseException(v105);
          if ( !newString )
            return 0;
          string = 0;
          v106 = WindowsDuplicateString_0(newString, &string);
          if ( v106 < 0 )
            __abi_WinRTraiseException(v106);
          return string;
        }
        v94 = v93 - 1;
        if ( !v94 )
        {
          newString = 0;
          v103 = WindowsCreateStringReference_0(L"MethodNotAllowed", 0x10u, &hstringHeader, &newString);
          if ( v103 < 0 )
            __abi_WinRTraiseException(v103);
          if ( !newString )
            return 0;
          string = 0;
          v104 = WindowsDuplicateString_0(newString, &string);
          if ( v104 < 0 )
            __abi_WinRTraiseException(v104);
          return string;
        }
        v95 = v94 - 1;
        if ( !v95 )
        {
          newString = 0;
          v101 = WindowsCreateStringReference_0(L"NotAcceptable", 0xDu, &hstringHeader, &newString);
          if ( v101 < 0 )
            __abi_WinRTraiseException(v101);
          if ( !newString )
            return 0;
          string = 0;
          v102 = WindowsDuplicateString_0(newString, &string);
          if ( v102 < 0 )
            __abi_WinRTraiseException(v102);
          return string;
        }
        v96 = v95 - 1;
        if ( !v96 )
        {
          newString = 0;
          v99 = WindowsCreateStringReference_0(L"ProxyAuthenticationRequired", 0x1Bu, &hstringHeader, &newString);
          if ( v99 < 0 )
            __abi_WinRTraiseException(v99);
          if ( !newString )
            return 0;
          string = 0;
          v100 = WindowsDuplicateString_0(newString, &string);
          if ( v100 < 0 )
            __abi_WinRTraiseException(v100);
          return string;
        }
        if ( v96 == 1 )
        {
          newString = 0;
          v97 = WindowsCreateStringReference_0(L"RequestTimeout", 0xEu, &hstringHeader, &newString);
          if ( v97 < 0 )
            __abi_WinRTraiseException(v97);
          if ( !newString )
            return 0;
          string = 0;
          v98 = WindowsDuplicateString_0(newString, &string);
          if ( v98 < 0 )
            __abi_WinRTraiseException(v98);
          return string;
        }
      }
      else
      {
        if ( v1 == 401 )
        {
          newString = 0;
          v89 = WindowsCreateStringReference_0(L"Unauthorized", 0xCu, &hstringHeader, &newString);
          if ( v89 < 0 )
            __abi_WinRTraiseException(v89);
          if ( !newString )
            return 0;
          string = 0;
          v90 = WindowsDuplicateString_0(newString, &string);
          if ( v90 < 0 )
            __abi_WinRTraiseException(v90);
          return string;
        }
        v69 = v1 - 301;
        if ( !v69 )
        {
          newString = 0;
          v87 = WindowsCreateStringReference_0(L"MovedPermanently", 0x10u, &hstringHeader, &newString);
          if ( v87 < 0 )
            __abi_WinRTraiseException(v87);
          if ( !newString )
            return 0;
          string = 0;
          v88 = WindowsDuplicateString_0(newString, &string);
          if ( v88 < 0 )
            __abi_WinRTraiseException(v88);
          return string;
        }
        v70 = v69 - 1;
        if ( !v70 )
        {
          newString = 0;
          v85 = WindowsCreateStringReference_0(L"Found", 5u, &hstringHeader, &newString);
          if ( v85 < 0 )
            __abi_WinRTraiseException(v85);
          if ( !newString )
            return 0;
          string = 0;
          v86 = WindowsDuplicateString_0(newString, &string);
          if ( v86 < 0 )
            __abi_WinRTraiseException(v86);
          return string;
        }
        v71 = v70 - 1;
        if ( !v71 )
        {
          newString = 0;
          v83 = WindowsCreateStringReference_0(L"SeeOther", 8u, &hstringHeader, &newString);
          if ( v83 < 0 )
            __abi_WinRTraiseException(v83);
          if ( !newString )
            return 0;
          string = 0;
          v84 = WindowsDuplicateString_0(newString, &string);
          if ( v84 < 0 )
            __abi_WinRTraiseException(v84);
          return string;
        }
        v72 = v71 - 1;
        if ( !v72 )
        {
          newString = 0;
          v81 = WindowsCreateStringReference_0(L"NotModified", 0xBu, &hstringHeader, &newString);
          if ( v81 < 0 )
            __abi_WinRTraiseException(v81);
          if ( !newString )
            return 0;
          string = 0;
          v82 = WindowsDuplicateString_0(newString, &string);
          if ( v82 < 0 )
            __abi_WinRTraiseException(v82);
          return string;
        }
        v73 = v72 - 1;
        if ( !v73 )
        {
          newString = 0;
          v79 = WindowsCreateStringReference_0(L"UseProxy", 8u, &hstringHeader, &newString);
          if ( v79 < 0 )
            __abi_WinRTraiseException(v79);
          if ( !newString )
            return 0;
          string = 0;
          v80 = WindowsDuplicateString_0(newString, &string);
          if ( v80 < 0 )
            __abi_WinRTraiseException(v80);
          return string;
        }
        v74 = v73 - 2;
        if ( !v74 )
        {
          newString = 0;
          v77 = WindowsCreateStringReference_0(L"TemporaryRedirect", 0x11u, &hstringHeader, &newString);
          if ( v77 < 0 )
            __abi_WinRTraiseException(v77);
          if ( !newString )
            return 0;
          string = 0;
          v78 = WindowsDuplicateString_0(newString, &string);
          if ( v78 < 0 )
            __abi_WinRTraiseException(v78);
          return string;
        }
        if ( v74 == 93 )
        {
          newString = 0;
          v75 = WindowsCreateStringReference_0(L"BadRequest", 0xAu, &hstringHeader, &newString);
          if ( v75 < 0 )
            __abi_WinRTraiseException(v75);
          if ( !newString )
            return 0;
          string = 0;
          v76 = WindowsDuplicateString_0(newString, &string);
          if ( v76 < 0 )
            __abi_WinRTraiseException(v76);
          return string;
        }
      }
    }
    goto LABEL_259;
  }
  if ( v1 == 300 )
  {
    newString = 0;
    v67 = WindowsCreateStringReference_0(L"MultipleChoices", 0xFu, &hstringHeader, &newString);
    if ( v67 < 0 )
      __abi_WinRTraiseException(v67);
    if ( !newString )
      return 0;
    string = 0;
    v68 = WindowsDuplicateString_0(newString, &string);
    if ( v68 < 0 )
      __abi_WinRTraiseException(v68);
    return string;
  }
  if ( v1 > 12 )
  {
    if ( v1 > 18 )
    {
      v53 = v1 - 19;
      if ( !v53 )
      {
        newString = 0;
        v65 = WindowsCreateStringReference_0(L"UnexpectedRedirection", 0x15u, &hstringHeader, &newString);
        if ( v65 < 0 )
          __abi_WinRTraiseException(v65);
        if ( !newString )
          return 0;
        string = 0;
        v66 = WindowsDuplicateString_0(newString, &string);
        if ( v66 < 0 )
          __abi_WinRTraiseException(v66);
        return string;
      }
      v54 = v53 - 1;
      if ( !v54 )
      {
        newString = 0;
        v63 = WindowsCreateStringReference_0(L"UnexpectedClientError", 0x15u, &hstringHeader, &newString);
        if ( v63 < 0 )
          __abi_WinRTraiseException(v63);
        if ( !newString )
          return 0;
        string = 0;
        v64 = WindowsDuplicateString_0(newString, &string);
        if ( v64 < 0 )
          __abi_WinRTraiseException(v64);
        return string;
      }
      v55 = v54 - 1;
      if ( !v55 )
      {
        newString = 0;
        v61 = WindowsCreateStringReference_0(L"UnexpectedServerError", 0x15u, &hstringHeader, &newString);
        if ( v61 < 0 )
          __abi_WinRTraiseException(v61);
        if ( !newString )
          return 0;
        string = 0;
        v62 = WindowsDuplicateString_0(newString, &string);
        if ( v62 < 0 )
          __abi_WinRTraiseException(v62);
        return string;
      }
      v56 = v55 - 1;
      if ( !v56 )
      {
        newString = 0;
        v59 = WindowsCreateStringReference_0(L"InsufficientRangeSupport", 0x18u, &hstringHeader, &newString);
        if ( v59 < 0 )
          __abi_WinRTraiseException(v59);
        if ( !newString )
          return 0;
        string = 0;
        v60 = WindowsDuplicateString_0(newString, &string);
        if ( v60 < 0 )
          __abi_WinRTraiseException(v60);
        return string;
      }
      if ( v56 == 1 )
      {
        newString = 0;
        v57 = WindowsCreateStringReference_0(L"MissingContentLengthSupport", 0x1Bu, &hstringHeader, &newString);
        if ( v57 < 0 )
          __abi_WinRTraiseException(v57);
        if ( !newString )
          return 0;
        string = 0;
        v58 = WindowsDuplicateString_0(newString, &string);
        if ( v58 < 0 )
          __abi_WinRTraiseException(v58);
        return string;
      }
    }
    else
    {
      if ( v1 == 18 )
      {
        newString = 0;
        v51 = WindowsCreateStringReference_0(L"UnexpectedStatusCode", 0x14u, &hstringHeader, &newString);
        if ( v51 < 0 )
          __abi_WinRTraiseException(v51);
        if ( !newString )
          return 0;
        string = 0;
        v52 = WindowsDuplicateString_0(newString, &string);
        if ( v52 < 0 )
          __abi_WinRTraiseException(v52);
        return string;
      }
      v37 = v1 - 13;
      if ( !v37 )
      {
        newString = 0;
        v49 = WindowsCreateStringReference_0(L"HttpsToHttpOnRedirection", 0x18u, &hstringHeader, &newString);
        if ( v49 < 0 )
          __abi_WinRTraiseException(v49);
        if ( !newString )
          return 0;
        string = 0;
        v50 = WindowsDuplicateString_0(newString, &string);
        if ( v50 < 0 )
          __abi_WinRTraiseException(v50);
        return string;
      }
      v38 = v37 - 1;
      if ( !v38 )
      {
        newString = 0;
        v47 = WindowsCreateStringReference_0(L"CannotConnect", 0xDu, &hstringHeader, &newString);
        if ( v47 < 0 )
          __abi_WinRTraiseException(v47);
        if ( !newString )
          return 0;
        string = 0;
        v48 = WindowsDuplicateString_0(newString, &string);
        if ( v48 < 0 )
          __abi_WinRTraiseException(v48);
        return string;
      }
      v39 = v38 - 1;
      if ( !v39 )
      {
        newString = 0;
        v45 = WindowsCreateStringReference_0(L"HostNameNotResolved", 0x13u, &hstringHeader, &newString);
        if ( v45 < 0 )
          __abi_WinRTraiseException(v45);
        if ( !newString )
          return 0;
        string = 0;
        v46 = WindowsDuplicateString_0(newString, &string);
        if ( v46 < 0 )
          __abi_WinRTraiseException(v46);
        return string;
      }
      v40 = v39 - 1;
      if ( !v40 )
      {
        newString = 0;
        v43 = WindowsCreateStringReference_0(L"OperationCanceled", 0x11u, &hstringHeader, &newString);
        if ( v43 < 0 )
          __abi_WinRTraiseException(v43);
        if ( !newString )
          return 0;
        string = 0;
        v44 = WindowsDuplicateString_0(newString, &string);
        if ( v44 < 0 )
          __abi_WinRTraiseException(v44);
        return string;
      }
      if ( v40 == 1 )
      {
        newString = 0;
        v41 = WindowsCreateStringReference_0(L"RedirectFailed", 0xEu, &hstringHeader, &newString);
        if ( v41 < 0 )
          __abi_WinRTraiseException(v41);
        if ( !newString )
          return 0;
        string = 0;
        v42 = WindowsDuplicateString_0(newString, &string);
        if ( v42 < 0 )
          __abi_WinRTraiseException(v42);
        return string;
      }
    }
    goto LABEL_259;
  }
  if ( v1 == 12 )
  {
    newString = 0;
    v35 = WindowsCreateStringReference_0(L"HttpToHttpsOnRedirection", 0x18u, &hstringHeader, &newString);
    if ( v35 < 0 )
      __abi_WinRTraiseException(v35);
    if ( !newString )
      return 0;
    string = 0;
    v36 = WindowsDuplicateString_0(newString, &string);
    if ( v36 < 0 )
      __abi_WinRTraiseException(v36);
    return string;
  }
  if ( v1 > 6 )
  {
    v21 = v1 - 7;
    if ( !v21 )
    {
      newString = 0;
      v33 = WindowsCreateStringReference_0(L"Timeout", 7u, &hstringHeader, &newString);
      if ( v33 < 0 )
        __abi_WinRTraiseException(v33);
      if ( !newString )
        return 0;
      string = 0;
      v34 = WindowsDuplicateString_0(newString, &string);
      if ( v34 < 0 )
        __abi_WinRTraiseException(v34);
      return string;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      newString = 0;
      v31 = WindowsCreateStringReference_0(L"ErrorHttpInvalidServerResponse", 0x1Eu, &hstringHeader, &newString);
      if ( v31 < 0 )
        __abi_WinRTraiseException(v31);
      if ( !newString )
        return 0;
      string = 0;
      v32 = WindowsDuplicateString_0(newString, &string);
      if ( v32 < 0 )
        __abi_WinRTraiseException(v32);
      return string;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      newString = 0;
      v29 = WindowsCreateStringReference_0(L"ConnectionAborted", 0x11u, &hstringHeader, &newString);
      if ( v29 < 0 )
        __abi_WinRTraiseException(v29);
      if ( !newString )
        return 0;
      string = 0;
      v30 = WindowsDuplicateString_0(newString, &string);
      if ( v30 < 0 )
        __abi_WinRTraiseException(v30);
      return string;
    }
    v24 = v23 - 1;
    if ( !v24 )
    {
      newString = 0;
      v27 = WindowsCreateStringReference_0(L"ConnectionReset", 0xFu, &hstringHeader, &newString);
      if ( v27 < 0 )
        __abi_WinRTraiseException(v27);
      if ( !newString )
        return 0;
      string = 0;
      v28 = WindowsDuplicateString_0(newString, &string);
      if ( v28 < 0 )
        __abi_WinRTraiseException(v28);
      return string;
    }
    if ( v24 == 1 )
    {
      newString = 0;
      v25 = WindowsCreateStringReference_0(L"Disconnected", 0xCu, &hstringHeader, &newString);
      if ( v25 < 0 )
        __abi_WinRTraiseException(v25);
      if ( !newString )
        return 0;
      string = 0;
      v26 = WindowsDuplicateString_0(newString, &string);
      if ( v26 < 0 )
        __abi_WinRTraiseException(v26);
      return string;
    }
    goto LABEL_259;
  }
  if ( v1 == 6 )
  {
    newString = 0;
    v19 = WindowsCreateStringReference_0(L"ServerUnreachable", 0x11u, &hstringHeader, &newString);
    if ( v19 < 0 )
      __abi_WinRTraiseException(v19);
    if ( !newString )
      return 0;
    string = 0;
    v20 = WindowsDuplicateString_0(newString, &string);
    if ( v20 < 0 )
      __abi_WinRTraiseException(v20);
    return string;
  }
  if ( !v1 )
  {
    newString = 0;
    v17 = WindowsCreateStringReference_0(L"Unknown", 7u, &hstringHeader, &newString);
    if ( v17 < 0 )
      __abi_WinRTraiseException(v17);
    if ( !newString )
      return 0;
    string = 0;
    v18 = WindowsDuplicateString_0(newString, &string);
    if ( v18 < 0 )
      __abi_WinRTraiseException(v18);
    return string;
  }
  v2 = v1 - 1;
  if ( !v2 )
  {
    newString = 0;
    v15 = WindowsCreateStringReference_0(L"CertificateCommonNameIsIncorrect", 0x20u, &hstringHeader, &newString);
    if ( v15 < 0 )
      __abi_WinRTraiseException(v15);
    if ( !newString )
      return 0;
    string = 0;
    v16 = WindowsDuplicateString_0(newString, &string);
    if ( v16 < 0 )
      __abi_WinRTraiseException(v16);
    return string;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    newString = 0;
    v13 = WindowsCreateStringReference_0(L"CertificateExpired", 0x12u, &hstringHeader, &newString);
    if ( v13 < 0 )
      __abi_WinRTraiseException(v13);
    if ( !newString )
      return 0;
    string = 0;
    v14 = WindowsDuplicateString_0(newString, &string);
    if ( v14 < 0 )
      __abi_WinRTraiseException(v14);
    return string;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    newString = 0;
    v11 = WindowsCreateStringReference_0(L"CertificateContainsErrors", 0x19u, &hstringHeader, &newString);
    if ( v11 < 0 )
      __abi_WinRTraiseException(v11);
    if ( !newString )
      return 0;
    string = 0;
    v12 = WindowsDuplicateString_0(newString, &string);
    if ( v12 < 0 )
      __abi_WinRTraiseException(v12);
    return string;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    newString = 0;
    v9 = WindowsCreateStringReference_0(L"CertificateRevoked", 0x12u, &hstringHeader, &newString);
    if ( v9 < 0 )
      __abi_WinRTraiseException(v9);
    if ( !newString )
      return 0;
    string = 0;
    v10 = WindowsDuplicateString_0(newString, &string);
    if ( v10 < 0 )
      __abi_WinRTraiseException(v10);
    return string;
  }
  if ( v5 != 1 )
  {
LABEL_259:
    newString = 0;
    v140 = WindowsCreateStringReference_0(L"Windows.Web.WebErrorStatus", 0x1Au, &hstringHeader, &newString);
    if ( v140 < 0 )
      __abi_WinRTraiseException(v140);
    if ( !newString )
      return 0;
    string = 0;
    v141 = WindowsDuplicateString_0(newString, &string);
    if ( v141 < 0 )
      __abi_WinRTraiseException(v141);
    return string;
  }
  string = 0;
  v6 = WindowsCreateStringReference_0(L"CertificateIsInvalid", 0x14u, &hstringHeader, &string);
  if ( v6 < 0 )
    __abi_WinRTraiseException(v6);
  if ( !string )
    return 0;
  newString = 0;
  v7 = WindowsDuplicateString_0(string, &newString);
  if ( v7 < 0 )
    __abi_WinRTraiseException(v7);
  return newString;
}

```

## disassembly

```asm
0x14001d710  mov     [rsp-8+arg_0], rbx
0x14001d715  push    rbp
0x14001d716  mov     rbp, rsp
0x14001d719  sub     rsp, 50h
0x14001d71d  mov     rax, cs:__security_cookie
0x14001d724  xor     rax, rsp
0x14001d727  mov     [rbp+var_8], rax
0x14001d72b  mov     edx, [rcx]
0x14001d72d  xor     ebx, ebx
0x14001d72f  mov     eax, 12Ch
0x14001d734  cmp     edx, eax
0x14001d736  jg      loc_14001DF89
0x14001d73c  jz      loc_14001DF3D
0x14001d742  cmp     edx, 0Ch
0x14001d745  jg      loc_14001DB98
0x14001d74b  jz      loc_14001DB4C
0x14001d751  cmp     edx, 6
0x14001d754  jg      loc_14001D9A7
0x14001d75a  jz      loc_14001D95B
0x14001d760  test    edx, edx
0x14001d762  jz      loc_14001D90F
0x14001d768  sub     edx, 1
0x14001d76b  jz      loc_14001D8C3
0x14001d771  sub     edx, 1
0x14001d774  jz      loc_14001D877
0x14001d77a  sub     edx, 1
0x14001d77d  jz      loc_14001D82B
0x14001d783  sub     edx, 1
0x14001d786  jz      short loc_14001D7DF
0x14001d788  cmp     edx, 1
0x14001d78b  jnz     loc_14001E7D1
0x14001d791  lea     r9, [rbp+string]; string
0x14001d795  mov     [rbp+string], rbx
0x14001d799  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d79d  lea     edx, [rbx+14h]; length
0x14001d7a0  lea     rcx, aCertificateisi; "CertificateIsInvalid"
0x14001d7a7  call    WindowsCreateStringReference_0
0x14001d7ac  test    eax, eax
0x14001d7ae  js      loc_14001E9F5
0x14001d7b4  mov     rcx, [rbp+string]; string
0x14001d7b8  test    rcx, rcx
0x14001d7bb  jz      loc_14001E9DB
0x14001d7c1  lea     rdx, [rbp+newString]; newString
0x14001d7c5  mov     [rbp+newString], rbx
0x14001d7c9  call    WindowsDuplicateString_0
0x14001d7ce  test    eax, eax
0x14001d7d0  js      loc_14001E9FD
0x14001d7d6  mov     rax, [rbp+newString]
0x14001d7da  jmp     loc_14001E9DE
0x14001d7df  lea     r9, [rbp+newString]; string
0x14001d7e3  mov     [rbp+newString], rbx
0x14001d7e7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d7eb  mov     edx, 12h; length
0x14001d7f0  lea     rcx, aCertificaterev; "CertificateRevoked"
0x14001d7f7  call    WindowsCreateStringReference_0
0x14001d7fc  test    eax, eax
0x14001d7fe  js      loc_14001EA05
0x14001d804  mov     rcx, [rbp+newString]; string
0x14001d808  test    rcx, rcx
0x14001d80b  jz      loc_14001E9DB
0x14001d811  lea     rdx, [rbp+string]; newString
0x14001d815  mov     [rbp+string], rbx
0x14001d819  call    WindowsDuplicateString_0
0x14001d81e  test    eax, eax
0x14001d820  js      loc_14001EA0D
0x14001d826  jmp     loc_14001E9D5
0x14001d82b  lea     r9, [rbp+newString]; string
0x14001d82f  mov     [rbp+newString], rbx
0x14001d833  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d837  mov     edx, 19h; length
0x14001d83c  lea     rcx, aCertificatecon; "CertificateContainsErrors"
0x14001d843  call    WindowsCreateStringReference_0
0x14001d848  test    eax, eax
0x14001d84a  js      loc_14001EA15
0x14001d850  mov     rcx, [rbp+newString]; string
0x14001d854  test    rcx, rcx
0x14001d857  jz      loc_14001E9DB
0x14001d85d  lea     rdx, [rbp+string]; newString
0x14001d861  mov     [rbp+string], rbx
0x14001d865  call    WindowsDuplicateString_0
0x14001d86a  test    eax, eax
0x14001d86c  js      loc_14001EA1D
0x14001d872  jmp     loc_14001E9D5
0x14001d877  lea     r9, [rbp+newString]; string
0x14001d87b  mov     [rbp+newString], rbx
0x14001d87f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d883  mov     edx, 12h; length
0x14001d888  lea     rcx, aCertificateexp; "CertificateExpired"
0x14001d88f  call    WindowsCreateStringReference_0
0x14001d894  test    eax, eax
0x14001d896  js      loc_14001EA25
0x14001d89c  mov     rcx, [rbp+newString]; string
0x14001d8a0  test    rcx, rcx
0x14001d8a3  jz      loc_14001E9DB
0x14001d8a9  lea     rdx, [rbp+string]; newString
0x14001d8ad  mov     [rbp+string], rbx
0x14001d8b1  call    WindowsDuplicateString_0
0x14001d8b6  test    eax, eax
0x14001d8b8  js      loc_14001EA2D
0x14001d8be  jmp     loc_14001E9D5
0x14001d8c3  lea     r9, [rbp+newString]; string
0x14001d8c7  mov     [rbp+newString], rbx
0x14001d8cb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d8cf  mov     edx, 20h ; ' '; length
0x14001d8d4  lea     rcx, aCertificatecom; "CertificateCommonNameIsIncorrect"
0x14001d8db  call    WindowsCreateStringReference_0
0x14001d8e0  test    eax, eax
0x14001d8e2  js      loc_14001EA35
0x14001d8e8  mov     rcx, [rbp+newString]; string
0x14001d8ec  test    rcx, rcx
0x14001d8ef  jz      loc_14001E9DB
0x14001d8f5  lea     rdx, [rbp+string]; newString
0x14001d8f9  mov     [rbp+string], rbx
0x14001d8fd  call    WindowsDuplicateString_0
0x14001d902  test    eax, eax
0x14001d904  js      loc_14001EA3D
0x14001d90a  jmp     loc_14001E9D5
0x14001d90f  lea     r9, [rbp+newString]; string
0x14001d913  mov     [rbp+newString], rbx
0x14001d917  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d91b  mov     edx, 7; length
0x14001d920  lea     rcx, aUnknown; "Unknown"
0x14001d927  call    WindowsCreateStringReference_0
0x14001d92c  test    eax, eax
0x14001d92e  js      loc_14001EA45
0x14001d934  mov     rcx, [rbp+newString]; string
0x14001d938  test    rcx, rcx
0x14001d93b  jz      loc_14001E9DB
0x14001d941  lea     rdx, [rbp+string]; newString
0x14001d945  mov     [rbp+string], rbx
0x14001d949  call    WindowsDuplicateString_0
0x14001d94e  test    eax, eax
0x14001d950  js      loc_14001EA4D
0x14001d956  jmp     loc_14001E9D5
0x14001d95b  lea     r9, [rbp+newString]; string
0x14001d95f  mov     [rbp+newString], rbx
0x14001d963  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d967  mov     edx, 11h; length
0x14001d96c  lea     rcx, aServerunreacha; "ServerUnreachable"
0x14001d973  call    WindowsCreateStringReference_0
0x14001d978  test    eax, eax
0x14001d97a  js      loc_14001EA55
0x14001d980  mov     rcx, [rbp+newString]; string
0x14001d984  test    rcx, rcx
0x14001d987  jz      loc_14001E9DB
0x14001d98d  lea     rdx, [rbp+string]; newString
0x14001d991  mov     [rbp+string], rbx
0x14001d995  call    WindowsDuplicateString_0
0x14001d99a  test    eax, eax
0x14001d99c  js      loc_14001EA5D
0x14001d9a2  jmp     loc_14001E9D5
0x14001d9a7  sub     edx, 7
0x14001d9aa  jz      loc_14001DB00
0x14001d9b0  sub     edx, 1
0x14001d9b3  jz      loc_14001DAB4
0x14001d9b9  sub     edx, 1
0x14001d9bc  jz      loc_14001DA68
0x14001d9c2  sub     edx, 1
0x14001d9c5  jz      short loc_14001DA1C
0x14001d9c7  cmp     edx, 1
0x14001d9ca  jnz     loc_14001E7D1
0x14001d9d0  lea     r9, [rbp+newString]; string
0x14001d9d4  mov     [rbp+newString], rbx
0x14001d9d8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001d9dc  mov     edx, 0Ch; length
0x14001d9e1  lea     rcx, aDisconnected; "Disconnected"
0x14001d9e8  call    WindowsCreateStringReference_0
0x14001d9ed  test    eax, eax
0x14001d9ef  js      loc_14001EA65
0x14001d9f5  mov     rcx, [rbp+newString]; string
0x14001d9f9  test    rcx, rcx
0x14001d9fc  jz      loc_14001E9DB
0x14001da02  lea     rdx, [rbp+string]; newString
0x14001da06  mov     [rbp+string], rbx
0x14001da0a  call    WindowsDuplicateString_0
0x14001da0f  test    eax, eax
0x14001da11  js      loc_14001EA6D
0x14001da17  jmp     loc_14001E9D5
0x14001da1c  lea     r9, [rbp+newString]; string
0x14001da20  mov     [rbp+newString], rbx
0x14001da24  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001da28  mov     edx, 0Fh; length
0x14001da2d  lea     rcx, aConnectionrese; "ConnectionReset"
0x14001da34  call    WindowsCreateStringReference_0
0x14001da39  test    eax, eax
0x14001da3b  js      loc_14001EA75
0x14001da41  mov     rcx, [rbp+newString]; string
0x14001da45  test    rcx, rcx
0x14001da48  jz      loc_14001E9DB
0x14001da4e  lea     rdx, [rbp+string]; newString
0x14001da52  mov     [rbp+string], rbx
0x14001da56  call    WindowsDuplicateString_0
0x14001da5b  test    eax, eax
0x14001da5d  js      loc_14001EA7D
0x14001da63  jmp     loc_14001E9D5
0x14001da68  lea     r9, [rbp+newString]; string
0x14001da6c  mov     [rbp+newString], rbx
0x14001da70  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001da74  mov     edx, 11h; length
0x14001da79  lea     rcx, aConnectionabor; "ConnectionAborted"
0x14001da80  call    WindowsCreateStringReference_0
0x14001da85  test    eax, eax
0x14001da87  js      loc_14001EA85
0x14001da8d  mov     rcx, [rbp+newString]; string
0x14001da91  test    rcx, rcx
0x14001da94  jz      loc_14001E9DB
0x14001da9a  lea     rdx, [rbp+string]; newString
0x14001da9e  mov     [rbp+string], rbx
0x14001daa2  call    WindowsDuplicateString_0
0x14001daa7  test    eax, eax
0x14001daa9  js      loc_14001EA8D
0x14001daaf  jmp     loc_14001E9D5
0x14001dab4  lea     r9, [rbp+newString]; string
0x14001dab8  mov     [rbp+newString], rbx
0x14001dabc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001dac0  mov     edx, 1Eh; length
0x14001dac5  lea     rcx, aErrorhttpinval; "ErrorHttpInvalidServerResponse"
0x14001dacc  call    WindowsCreateStringReference_0
0x14001dad1  test    eax, eax
0x14001dad3  js      loc_14001EA95
0x14001dad9  mov     rcx, [rbp+newString]; string
0x14001dadd  test    rcx, rcx
0x14001dae0  jz      loc_14001E9DB
0x14001dae6  lea     rdx, [rbp+string]; newString
0x14001daea  mov     [rbp+string], rbx
0x14001daee  call    WindowsDuplicateString_0
0x14001daf3  test    eax, eax
0x14001daf5  js      loc_14001EA9D
0x14001dafb  jmp     loc_14001E9D5
0x14001db00  lea     r9, [rbp+newString]; string
0x14001db04  mov     [rbp+newString], rbx
0x14001db08  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001db0c  mov     edx, 7; length
0x14001db11  lea     rcx, aTimeout; "Timeout"
0x14001db18  call    WindowsCreateStringReference_0
0x14001db1d  test    eax, eax
0x14001db1f  js      loc_14001EAA5
0x14001db25  mov     rcx, [rbp+newString]; string
0x14001db29  test    rcx, rcx
0x14001db2c  jz      loc_14001E9DB
0x14001db32  lea     rdx, [rbp+string]; newString
0x14001db36  mov     [rbp+string], rbx
0x14001db3a  call    WindowsDuplicateString_0
0x14001db3f  test    eax, eax
0x14001db41  js      loc_14001EAAD
0x14001db47  jmp     loc_14001E9D5
0x14001db4c  lea     r9, [rbp+newString]; string
0x14001db50  mov     [rbp+newString], rbx
0x14001db54  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001db58  mov     edx, 18h; length
0x14001db5d  lea     rcx, aHttptohttpsonr; "HttpToHttpsOnRedirection"
0x14001db64  call    WindowsCreateStringReference_0
0x14001db69  test    eax, eax
0x14001db6b  js      loc_14001EAB5
0x14001db71  mov     rcx, [rbp+newString]; string
0x14001db75  test    rcx, rcx
0x14001db78  jz      loc_14001E9DB
0x14001db7e  lea     rdx, [rbp+string]; newString
0x14001db82  mov     [rbp+string], rbx
0x14001db86  call    WindowsDuplicateString_0
0x14001db8b  test    eax, eax
0x14001db8d  js      loc_14001EABD
0x14001db93  jmp     loc_14001E9D5
0x14001db98  cmp     edx, 12h
0x14001db9b  jg      loc_14001DD98
0x14001dba1  jz      loc_14001DD4C
0x14001dba7  sub     edx, 0Dh
0x14001dbaa  jz      loc_14001DD00
0x14001dbb0  sub     edx, 1
0x14001dbb3  jz      loc_14001DCB4
0x14001dbb9  sub     edx, 1
0x14001dbbc  jz      loc_14001DC68
0x14001dbc2  sub     edx, 1
0x14001dbc5  jz      short loc_14001DC1C
0x14001dbc7  cmp     edx, 1
0x14001dbca  jnz     loc_14001E7D1
0x14001dbd0  lea     r9, [rbp+newString]; string
0x14001dbd4  mov     [rbp+newString], rbx
0x14001dbd8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001dbdc  mov     edx, 0Eh; length
0x14001dbe1  lea     rcx, aRedirectfailed; "RedirectFailed"
0x14001dbe8  call    WindowsCreateStringReference_0
0x14001dbed  test    eax, eax
0x14001dbef  js      loc_14001EAC5
0x14001dbf5  mov     rcx, [rbp+newString]; string
0x14001dbf9  test    rcx, rcx
0x14001dbfc  jz      loc_14001E9DB
0x14001dc02  lea     rdx, [rbp+string]; newString
0x14001dc06  mov     [rbp+string], rbx
0x14001dc0a  call    WindowsDuplicateString_0
0x14001dc0f  test    eax, eax
0x14001dc11  js      loc_14001EACD
0x14001dc17  jmp     loc_14001E9D5
0x14001dc1c  lea     r9, [rbp+newString]; string
0x14001dc20  mov     [rbp+newString], rbx
0x14001dc24  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001dc28  mov     edx, 11h; length
0x14001dc2d  lea     rcx, aOperationcance; "OperationCanceled"
0x14001dc34  call    WindowsCreateStringReference_0
0x14001dc39  test    eax, eax
  ... truncated ...
```
